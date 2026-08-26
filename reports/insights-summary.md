# Insights Summary


# E-Commerce Funnel & Purchase Path Intelligence

## Overview


This document summarizes the key business insights derived from the session-level e-commerce funnel and purchase-path analysis.

The analysis covers five monthly datasets from **October 2019 to February 2020** and uses customer-session behavior to understand funnel drop-off, purchase-path contribution, revenue, basket economics, and customer behavior. The analysis is based on **20.69 million event records** after combining the monthly files, with sessions used as the primary unit for funnel analysis.

---

## Funnel Performance


- The strict funnel begins with **4,280,701 View sessions**.
- **788,430 sessions** contain both View and Cart activity, resulting in an **18.42% View → View+Cart conversion rate**.
- This represents an **81.58% drop-off** between View and View+Cart, making the first major funnel loss point.
- Only **106,526 sessions** progress from View + Cart to Purchase within the same session.
- The **View+Cart → Purchase conversion rate is 13.51%**, corresponding to an **86.49% drop-off**.
- The largest relative funnel bottleneck is therefore the transition from **cart activity to purchase**.

---

## Purchase Path Performance


- **Immediate purchases account for 106,526 purchase sessions**, representing **68.45% of all purchase sessions**.
- Immediate purchases generate **4.34M in revenue**, representing **68.40% of total purchase-path revenue**.
- **Delayed purchases account for 48,250 sessions**, representing **31.01% of purchase sessions**.
- Delayed purchases generate approximately **1.97M in revenue**, contributing **30.99% of revenue**.
- **Direct purchases represent only 841 sessions**, or **0.54% of purchase sessions**, and contribute **0.61% of revenue**.
- The business therefore generates the majority of purchasing activity through Immediate sessions, while the Delayed path remains a substantial secondary revenue stream.

---

## Revenue Performance


- The analyzed purchase paths generate approximately **6.35M in total purchase-path revenue**.
- **Immediate purchases contribute 4.34M**, making them the primary revenue source.
- **Delayed purchases contribute 1.97M**, showing that later-session conversion represents a meaningful commercial opportunity.
- Direct purchasing contributes only about **38.8K**, so the Direct segment is comparatively small despite having the highest reported AOV.
- Revenue share closely follows purchase-session share for Immediate and Delayed customers, indicating broadly similar revenue contribution per purchasing session between these two paths.

---

## Purchase Economics


- **Immediate AOV is approximately 40.76**, with an average basket size of **8.25 items**.
- **Delayed AOV is approximately 40.77**, with an average basket size of **8.28 items**.
- Immediate and Delayed customers therefore show **very similar order economics**, despite following different purchase journeys.
- The median basket size is **6 items** for both Immediate and Delayed customers.
- Direct purchases show a higher reported AOV of approximately **46.08** and an average basket size of **9.55 items**.
- Because the Direct segment contains only **841 purchase sessions**, its higher AOV should be treated cautiously and not prioritized without further validation.

---

## Customer Journey Implications


- The analysis demonstrates that **cart creation does not necessarily translate into immediate purchase**.
- The existence of **48,250 Delayed purchase sessions** shows that a meaningful portion of customers convert after earlier engagement rather than completing the transaction immediately.
- Since Delayed customers generate approximately **31% of purchase-path revenue**, recovery and re-engagement strategies represent a potentially meaningful commercial lever.
- The relatively similar AOV between Immediate and Delayed customers suggests that the opportunity is primarily to improve **conversion timing and journey completion**, rather than relying on a large difference in order value.

---

## Product & Category Analysis


- The notebook extends the analysis to **top products and categories by purchase-session and revenue contribution**.
- Product-level analysis is segmented by Immediate, Delayed, and Direct purchase paths, allowing high-performing products to be evaluated in the context of customer journey type.
- The analysis is intended to identify products with strong purchasing demand and revenue contribution for merchandising prioritization.
- However, the underlying dataset has substantial missingness in `category_code` and `brand`, so detailed category/brand conclusions should be interpreted with appropriate caution.

---

## Customer & Time Analysis


- The notebook analyzes purchase behavior by **month, weekday, and hour of day** to identify demand concentration.
- It also classifies purchasing users as **New or Returning** based on observed purchase history.
- These dimensions provide a basis for identifying changes in customer mix, trading periods, and purchasing activity over time.
- The current summary does not assign specific weekday, hourly, or New-versus-Returning leaders where the underlying output is not directly available in the extracted results.

---

## Data Quality Considerations


- The combined dataset contains **20,692,840 event rows** before removing records with missing `user_session`.
- There are **4,598 rows with missing user sessions**, so these rows are excluded from session-based funnel analysis.
- `category_code` has **20,339,246 missing values**, creating a major limitation for category-level analysis.
- `brand` has **8,757,117 missing values**, limiting the reliability of brand-level conclusions.
- The funnel metrics therefore have stronger analytical reliability at the **session and event-type level** than at the brand/category level.

---

## Key Business Takeaways


- The largest funnel loss occurs between **View and View+Cart**, where **81.58% of sessions drop out**.
- The **View+Cart → Purchase stage is the strongest immediate conversion opportunity**, with an **86.49% drop-off**.
- **Immediate customers generate 68.40% of revenue**, making this the dominant purchasing path.
- **Delayed customers generate 30.99% of revenue**, making delayed conversion a strategically important secondary opportunity.
- Immediate and Delayed customers have almost identical AOVs, indicating that improving journey completion may be more important than increasing order value.
- Direct purchases are small in volume and revenue contribution, so their higher AOV should not drive the primary business strategy.
- Product, category, timing, and customer-type analysis can support more targeted merchandising, campaign timing, and retention decisions.
- Data-quality limitations—particularly missing category and brand values—should be considered before making granular merchandising decisions.

---

## Recommendations


- **Prioritize cart-to-purchase conversion:** investigate checkout friction, payment experience, shipping/price visibility, and other barriers that may explain the **86.49% drop-off**.
- **Build delayed-conversion recovery journeys:** use reminders, cart persistence, personalized follow-ups, and retargeting to capture customers who do not purchase immediately.
- **Protect the Immediate path:** since it generates **68.40% of revenue**, improvements should not negatively affect the existing high-volume conversion journey.
- **Use product and category analysis for merchandising:** prioritize high-contribution products while improving the completeness of category and brand data.
- **Use time and customer-mix analysis operationally:** align promotional activity and retention initiatives with the strongest observed purchasing periods and customer segments.

---

## Conclusion


The analysis shows that the major commercial challenge is **not lack of purchase activity, but substantial leakage at the customer-journey stages before purchase completion**. The strongest opportunity is to improve the transition from **Cart to Purchase**, while treating the **Delayed purchase path as a meaningful source of recoverable demand and revenue**.

Overall, the project converts high-volume event data into a practical decision framework covering **funnel optimization, purchase-path strategy, revenue contribution, basket economics, customer behavior, timing, and merchandising**.
