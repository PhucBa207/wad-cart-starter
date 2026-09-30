# AI-LOG

## AI Tool Used

GitHub Copilot was used to inspect the starter repository, create the project harness and assignment brief, implement `cartTotal`, add focused tests, and run the project checks.

## What Copilot Produced

- Read `README.md`, `package.json`, `AGENTS.md`, `src/cart.js`, and `test/cart.test.js` before implementing the function.
- Created `AGENTS.md` with the plain JavaScript/npm stack, project commands, repository rules, explicit `Never` rules, and the no-external-dependencies constraint.
- Added the `lint` script to `package.json`:
  `node --check src/cart.js && node --check test/cart.test.js`.
- Created `.github/workflows/ci.yml` to run on every push with Node.js 20, `npm install`, `npm test`, and `npm run lint`.
- Created `BRIEF.md` describing the goal, allowed files, contract, edge cases, worked example, and constraints.
- Implemented `cartTotal(items, options)` in `src/cart.js`.
- Added four focused tests to `test/cart.test.js` for an empty cart, the exact free-shipping threshold, a negative price, and a non-integer quantity.

## Changes Accepted

The accepted implementation in `src/cart.js`:

- Returns `0` for an empty cart.
- Validates that prices are not negative and quantities are positive integers, throwing `RangeError` when invalid.
- Sums `price * qty` into the subtotal.
- Applies VAT to the subtotal.
- Uses zero shipping when the subtotal reaches `freeShipFrom`; otherwise uses `shipFee`.
- Returns the rounded total as a number.

The existing worked-example test remains unchanged and still expects `467400`.

## Rejected Changes or Suggestions

No changes or suggestions were rejected. No alternative implementation was recorded as proposed and discarded.

## Manual Work

The student supplied the assignment specification, repository constraints, and required workflow to GitHub Copilot.

The student manually ran and checked the required project commands, including `npm test`, `npm run lint`, and `git diff`, and reviewed the resulting test output and changes.

The student also reviewed the AI-generated implementation, tests, harness changes, and assignment brief before accepting them.

## Evidence and Checks

- Before implementation, `npm test` failed at `src/cart.js` with `Error: not implemented`.
- After implementation and test additions, `npm test` passed all five tests.
- `npm run lint` passed using Node's built-in syntax checker.
- The final implementation diff is in `src/cart.js` and `test/cart.test.js`; the lint script diff is in `package.json`.
- The setup files can be checked directly in `AGENTS.md`, `BRIEF.md`, and `.github/workflows/ci.yml`.
