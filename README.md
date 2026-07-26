# German tax system, visualised

**https://tax-de.wbg.gg**

An interactive look at how fast the German tax burden grows with income
(income tax 2024 per §32a EStG, optionally including employee social contributions).

## How to read the chart

The vertical axis is income. The horizontal axis is how one euro splits up:

- the **width** of a band is the marginal burden on the *next* euro earned
- the **area** of a band up to the slider is the amount actually paid

So the tax curve is a fixed backdrop, and the slider projects your income onto it.
Everything below the slider line is paid; above it is a faint preview of what comes next.

`Net | Social contributions | Tax` — left to right.

## Details

- Income tax follows the 2024 tariff formula (§32a EStG): basic allowance 11,604 €,
  two progressive zones, 42 % from 66,760 € and 45 % from 277,825 €.
- With social contributions enabled, the value is a **gross salary** and the figures use
  the 2024 employee rates: pension 9.3 %, unemployment 1.3 %, health 8.15 %
  (incl. half of the average supplementary rate), long-term care 2.3 % (no children).
  Contribution ceilings: 62,100 € (health/care) and 90,600 € (pension/unemployment, West).
- Pension, health and care contributions reduce the taxable base as
  *Vorsorgeaufwendungen* (simplified *Vorsorgepauschale*). Unemployment insurance does not.
- Without social contributions, the value on the slider is the **taxable income** (zvE) directly.

Not included: church tax, solidarity surcharge, *Werbungskosten*, other deductions,
splitting for married couples, Saxony's differing care-insurance split.
This is a teaching tool, not a tax return.

## Development

A single self-contained `index.html` — no build step, no dependencies.
Open it in a browser; there is nothing to install.

Deployment is GitHub Pages serving `main` at `/` directly, so every push to `main`
is live once Pages has rebuilt. The custom domain comes from the `CNAME` file,
pointed at `whiteblackgoose.github.io` by DNS.
