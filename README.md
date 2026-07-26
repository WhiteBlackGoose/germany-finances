# Germany: taxes and benefits, visualised

**https://finances-de.wbg.gg**

An interactive look at what the German state takes from you and what it gives back —
wage tax and social contributions 2024, plus citizen's benefit, housing benefit and
child benefit. Two views, one slider, switchable between monthly and yearly figures.

## What you pay — read the *area*

The vertical axis is gross salary. The horizontal axis is how one euro splits up:

- the **width** of a band is the marginal burden on the *next* euro earned
- the **area** of a band up to the slider is the amount actually paid

So the tax curve is a fixed backdrop, and the slider projects your income onto it.
Everything below the slider line is paid; above it is a faint preview of what comes next.

`Net | Social contributions | Tax | Church tax` — left to right.

The two dashed teal lines are the contribution ceilings. Crossing them makes the
marginal burden *drop*, which is the most counter-intuitive feature of the system.

## What you receive — read the *length*

Same vertical axis, but horizontally an amount rather than a share: citizen's benefit,
housing benefit, child benefit and net pay stacked into the disposable income. The
slider line itself is split into those four pieces, so you can read the composition at
any income directly off it.

- **Citizen's benefit** — standard needs plus housing, with income credited under the
  §11b SGB II allowance steps (100 € / 20 % / 30 % / 10 %)
- **Housing benefit** — the §19 WoGG formula with the a/b/c parameters of Anlage 2 and
  the rent ceilings of Anlage 1 by rent level I–VII
- **Child benefit** — 250 € per child

Citizen's benefit takes precedence, so housing benefit only starts where the former
ends; the green line marks that threshold.

## What you can set

- **Tax class I–VI.** III applies the splitting tariff, II adds the single-parent
  allowance, VI drops the employee and special-expenses allowances, and V/VI use the
  separate formula of §39b (2) sentence 7 EStG instead of the bracket tariff.
- **Region.** West/East changes the pension and unemployment ceiling
  (90,600 € / 89,400 €); Saxony additionally shifts the care-insurance split to the
  employee (2.2 % instead of 1.7 %).
- **Church tax** — 8 % (Bavaria, Baden-Württemberg) or 9 % of the wage tax.
- **Health insurance surcharge** — the fund-specific rate, 1.7 % on average in 2024.
- **No children** — adds the 0.6 % care-insurance surcharge, paid by the employee alone.

## Accuracy

Tax figures follow the BMF Programmablaufplan 2024 and were checked against its
official Prüftabelle for all six tax classes: agreement within ~15 €. The remaining
gap is the statutory rounding of the taxable amount down to a multiple of 36 €
(§39b (2) sentence 6), which is deliberately not reproduced — a step function would
destroy the marginal-rate curve that the whole chart is built on.

Contributions to pension, health and care insurance reduce the tax base via the
*Vorsorgepauschale*; unemployment insurance does not. Health insurance counts at the
reduced rate (7.0 % + half the surcharge) for that deduction, while 7.3 % + half the
surcharge is actually paid.

Not included: solidarity surcharge, private health insurance, real *Werbungskosten*
beyond the standard allowance, child tax allowances, and the retroactive 2024 increase
of the basic allowance to 11,784 € (the original 11,604 € tariff is used throughout).

On the benefits side the model is coarser: no minijob or transition-zone relief on
social contributions (so net pay is understated below ~2,000 €/month, exactly where
benefits matter), no child supplement, no single-parent extra needs, no heating or
climate component in the housing benefit, and children are costed at the 6–13 age band.

This is a teaching tool, not a payroll run.

## Development

A single self-contained `index.html` — no build step, no dependencies.
Open it in a browser; there is nothing to install.

Deployment is GitHub Pages serving `main` at `/` directly, so every push to `main`
is live once Pages has rebuilt. The custom domain comes from the `CNAME` file,
pointed at `whiteblackgoose.github.io` by DNS.
