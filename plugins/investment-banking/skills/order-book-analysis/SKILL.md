---
name: order-book-analysis
description: Summarise the order book of an equity or bond offering during bookbuilding — demand by price or spread level, coverage, investor type and quality, price sensitivity and concentration — to support the pricing decision. Use when the user shares an order book or demand sheet for an IPO, follow-on, block or bond issue and asks for a book summary, demand curve, coverage analysis or pricing read.
license: Apache-2.0
metadata:
  industry: finance
  scenario: ib/ecm-dcm
  author: CorpSkill
  version: 0.1.0
---

# Order Book Analysis

Turn a list of orders into the picture the syndicate desk and the issuer need to set the price: how much demand there is at each level, who it comes from, and how much of it will still be there after the price is fixed.

Order books contain confidential client information. Work only inside the firm's approved environment, and report investor names only to those entitled to see them.

## Workflow

1. **Load and check the book**: one row per order with investor, type, amount (shares or nominal), price limit or spread limit (or "at market / strike"), time of entry and changes, any conditions, and the desk's quality grade if given. Check for duplicates across bookrunners, orders in the wrong units or currency, and stale entries.
2. **Build the demand curve**: cumulative demand at each price step (equity: down from the top of the range; bonds: at each spread from guidance tighter). Demand at a level = strike / market orders + all limit orders that are still good at that level.
3. **Compute coverage** at each level: demand ÷ deal size (state whether the base includes the over-allotment option or any upsize).
4. **Segment the demand** at the likely pricing level:
   - by investor type (long-only, hedge fund, sovereign / official, pension and insurance, bank treasury, private bank / retail, corporate)
   - by quality grade, if supplied — otherwise say that quality cannot be assessed from the data
   - by geography
   - by order size; share of the top 5 and top 10 orders
5. **Assess price sensitivity**: how much demand is lost at each step tighter or higher; which large orders drop out and where; how many orders are limit orders close to the level.
6. **Assess the quality of the number**: inflated orders (investors bidding above what they want in expectation of being cut), orders conditional on size or price, momentum in the book (still growing, flat, or shrinking after an update), and anchor or cornerstone demand.
7. **Give the read**: the levels at which the deal is covered by high-quality demand alone; the level at which the book thins out; what an upsize would do.

## Output format

```
## Book snapshot — [time], deal size [x]
Total demand · number of orders · coverage at [reference level]

## Demand curve
| Price / spread | Cumulative demand | Coverage | Orders | Demand lost vs previous step |

## Composition at [level]
| By type | Amount | % |      | By geography | % |
Top 10 orders: [x]% of demand

## Price sensitivity
Named drop-outs by level (where the reader is entitled to names)

## Observations
Quality, inflation, momentum, concentration.

## Pricing read
```

For a book that is updated through the day, add a comparison with the previous snapshot: new orders, increases, reductions, cancellations.

## Rules

- Headline coverage is not the conclusion. Ten times covered by accounts that will sell on day one supports a lower price than three times covered by holders.
- State which orders you treated as good at each level and how conditional orders were handled.
- Describe; do not recommend a price unless asked. The pricing decision belongs to the issuer with the bookrunners.

## Limits

The analysis reflects the book as supplied at one moment. Quality grades and knowledge of investor behaviour come from the desk, not from this skill.
