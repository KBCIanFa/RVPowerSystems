## V2 — Release Notes

### New Features

**Regional Pricing & Currency**
Product recommendations in the Components tab now show region-specific pricing and links. Switch between AU, US, UK, CA, and EU via the 🛒 Shop selector in the settings bar. The currency label updates automatically (AUD, USD, GBP, CAD, EUR).

**Appliance Reference Lookup**
A searchable library of 42 common RV appliances across 7 categories — lighting, fridges, kitchen, climate, tech, medical, water, and other. Click **📋 Browse Appliances** in the Loads tab to find typical wattage and usage figures without leaving the app.

**Input Validation**
Appliance entries now validate in real time. Invalid watts or hours (negative numbers, values over 24 hours, non-numeric input) are blocked with inline warnings displayed per row. High-wattage entries (>5000W) show a caution rather than a hard block.

**Sizing Alerts**
The Sizing tab now surfaces contextual warnings for edge cases — very heavy systems, high solar current at 12V, roof space overruns, slow recharge times, and energy deficits. Alerts appear automatically based on your load profile.

**Price Disclaimers**
All component prices are now labelled as estimated (est.) with a tooltip noting prices should be verified with retailers before purchase.

---

### Bug Fixes

- **NaN cascade on inverter efficiency** — if the inverter or solar efficiency selector returned an unparseable value, `totalWh` and `solarW` would silently become `NaN`. Both values are now clamped with a minimum floor and safe fallback.
- **Component qty lost on deselect** — deselecting and reselecting a component in the Components tab was resetting the quantity back to 1. Quantity is now preserved across the toggle.
- **Yuasa product URL** — corrected from `yuasa.com.au` to `yuasabatteries.com.au`.

---

### Quality

- 62-test suite (unit, functional, regression, production readiness) — all passing
- No debug output in production build
- File size 239KB
