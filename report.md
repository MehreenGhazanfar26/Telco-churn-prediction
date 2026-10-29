# Customer Churn Report: Telecom Retention Plan

**Prepared by:** [Your Name]
**Data:** 7,043 telecom customers (public Kaggle dataset)

---

## 1. The Problem and the Goal

About **1 in 4 customers (26.5%)** in this data left the company. Every customer who leaves takes their monthly revenue with them, and winning a new customer usually costs more than keeping an existing one.

**Goal:** find the customers who are likely to leave, so the company can offer help (a call or a discount) only to the people who need it.

---

## 2. What We Found

1. **Contract type matters most.** Customers on month-to-month plans left about **43%** of the time. One-year customers left about 11%, and two-year customers about 3%.
2. **New customers leave early.** Customers who left stayed about **17 months** on average. Customers who stayed had been with the company about 37 months.
3. **Fiber optic customers leave more.** About **42%** of fiber optic customers left, compared with about 19% of DSL customers.
4. **Payment method and support matter.** Customers paying by electronic check left about 45% of the time, which is the highest among payment methods. Customers without tech support left about 42%, compared with about 15% for those with it.
5. **Senior citizens leave more.** About 42% left, compared with about 24% of other customers.

*These are patterns in the data. They show which customers are at higher risk, but they do not prove the cause.*

---

## 3. What the Model Can Do

We built a model that gives every customer a **churn risk score**. The company then chooses a cutoff: customers above it are flagged for a retention offer.

**Result on customers the model had never seen (1,409 customers, 374 of whom actually left):**

| | Number |
|---|---|
| Leavers the model caught | 342 of 374 (**91%**) |
| Leavers the model missed | 32 |
| Customers flagged who would have stayed anyway | 436 |

About 44 of every 100 flagged customers were real leavers.

**Estimated cost comparison (using example costs, see Section 5):**

| Strategy | Estimated cost |
|---|---|
| Do nothing (call nobody) | 1,870 |
| Call every customer | 1,035 |
| **Use the model** | **596** |

The model cuts the estimated cost by about **68%** compared with doing nothing, and about **42%** compared with calling everyone.

**If the retention team can only call 100 customers:** we call the 100 customers with the highest risk scores. About **73 of them** were real leavers. A random list of 100 would find only about 27, so the model is about 2.7 times better than random.

---

## 4. Our Recommendations

1. **Move month-to-month customers to one-year plans.** Offer a small discount for switching. This targets the biggest risk group.
2. **Look into fiber optic customers.** Check whether the cause is price, service quality, or competition.
3. **Focus on the first 6 to 12 months.** Better onboarding and early offers can help new customers settle in.
4. **Encourage automatic payment.** Customers on automatic bank or card payment left far less often than electronic check users.
5. **Bundle support services.** Customers with tech support and online security leave about half as often.

---

## 5. Risks and Limits

- **The costs are examples.** We assumed a retention offer costs 1 unit and a lost customer costs 5 units. The real numbers will change the best cutoff and the savings.
- **An offer may not always work.** The savings assume every flagged customer stays after an offer. In real life, some will leave anyway, so actual savings will be lower.
- **Patterns are not proof of cause.** For example, fiber optic customers may leave because of price, service, or something else.
- **One snapshot in time.** We could not check how the model performs as customer behavior changes.

---

## 6. Next Steps

1. **Get the real costs** (offer cost and customer value) from the finance team, then set the cutoff again.
2. **Run a small pilot.** Offer retention deals to a flagged group and compare it with an unflagged group. This shows how many customers an offer really keeps.
3. **Re-check the model every few months** with fresh data, and update it if its performance drops.
