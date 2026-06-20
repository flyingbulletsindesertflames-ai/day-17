what we learn: Today's challenge: take a raw CSV of fuel-economy data across five fuel types (CNG, Diesel, E85, EV, Petrol) and turn it into a real decision-making tool — not just a chart, but a dashboard that tells your specific car whether switching fuels makes sense.

What we built
Starting from a Hyundai Creta 1.6 Diesel (9 years old, 1,000 km/month), we computed cost/km, CO₂/km, and maintenance/km per fuel type, broke costs down by vehicle-age bucket, and modeled the actual "E85 paradox" — the fact that E85 is cheaper at the pump but can cost more per km to actually drive, depending on mileage. That all fed into a single-file HTML dashboard: five KPI cards, a bar chart, a donut chart, a multi-line age trend chart, and an animated gauge — every one of them hand-built in raw SVG and vanilla JS, no charting library, no CDN.

What we learned

How to go from a pandas groupby straight into a clean JS data object that drives every chart from one source of truth, instead of hardcoding numbers into markup.
The actual math behind SVG arcs — polarToCartesian + describeArc — and the "stroke-as-ring" trick for drawing a donut chart without manual pie-slice geometry.
Animating an SVG gauge using stroke-dasharray/stroke-dashoffset, and catching a real directional bug: the fill was animating from the high end of the gauge instead of the low end — a good reminder to trace through your own coordinate math instead of trusting that "it looks roughly right."
That glassmorphism + a dark navy palette + consistent design tokens (colors, radius, fonts as CSS variables) makes a dashboard feel cohesive without needing a UI framework.
Net result for the Creta: Diesel runs ₹4.67/km, E85 would cost ₹6.37/km to actually drive despite being 18% cheaper at the pump — score 5.7/10. Clean, not cheap, yet.
