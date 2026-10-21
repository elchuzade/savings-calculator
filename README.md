# Too Late to Start?

A savings quest by [abbox](https://www.abbox.com/), live at [savings-calculator.abbox.com](https://savings-calculator.abbox.com).

A small calculator for the question "is it too late to start investing?"

There are four linked sliders: **goal amount**, **target age**, **start age** and **monthly amount**. Pick which one to calculate, move the other three, and the fourth updates live. The page also shows:

- how much of the end result is your own money vs. growth
- a curve of the monthly amount needed for every possible start age
- what waiting 1, 3, 5 or 10 years would cost

## How it works

Everything runs in one `index.html` file in the browser, with no backend, no build step and no dependencies beyond Google Fonts (Geist, Geist Mono, Comfortaa). It assumes a fixed monthly contribution and a steady average return, compounded monthly:

- Future value: `FV = P × ((1 + i)^n − 1) / i`
- Monthly amount: `P = FV × i / ((1 + i)^n − 1)`
- Months needed: `n = ln(FV × i / P + 1) / ln(1 + i)`

where `i` is the yearly return divided by 12 and `n` is the number of months.

## Run locally

Open `index.html` in a browser.

## Deployment

Deployed on Vercel as a static site (no build step, `index.html` at the root), with DNS on Cloudflare pointing `savings-calculator.abbox.com` at Vercel. Pushing to `main` redeploys.

## Disclaimer

This is a thinking tool, not financial advice. Real returns vary and are not guaranteed.
