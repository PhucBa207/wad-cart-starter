# Project Harness

## Stack

- Plain JavaScript.
- Existing npm setup from `package.json` and `package-lock.json`.
- No external runtime or development dependencies may be added.

## Commands

From the repository root:

```bash
npm install
npm test
```

`npm test` is the project test gate. Run it before and after changes.

## Repository Rules

- Implement `cartTotal(items, options)` in `src/cart.js`.
- Keep the public API and existing npm setup unchanged.
- Follow the README contract: calculate subtotal, VAT, and shipping; waive shipping when the subtotal reaches `freeShipFrom`; return `0` for an empty cart; throw `RangeError` for a negative price or a non-positive, non-integer quantity; and return a whole-dong number.
- Add or update focused tests in `test/` when behavior changes.
- Keep changes small and readable, and inspect the diff before finishing.

## Never

- Never add external dependencies.
- Never modify `package-lock.json` by hand.
- Never remove or weaken tests to make `npm test` pass.
