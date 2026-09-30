# Brief: Implement `cartTotal`

## Goal

Implement the exported `cartTotal(items, options)` function in `src/cart.js`.

## Files and Scope

The assistant may modify:

- `src/cart.js`, where the implementation belongs.
- Files under `test/`, when adding or updating focused tests for the specified behavior.

Do not modify unrelated project files, including the package configuration, lockfile, README, harness rules, workflow, or assignment documentation.

## Contract

The function accepts:

- `items`: an array of objects with the form `[{ name, price, qty }]`.
- `options`: an object with the form `{ vatRate, freeShipFrom, shipFee }`.

For a non-empty cart:

1. Calculate `subtotal` as the sum of `price * qty` for every item.
2. Calculate VAT as `vatRate` applied to the subtotal.
3. Set shipping to `0` when `subtotal >= freeShipFrom`; otherwise use `shipFee`.
4. Return `subtotal + VAT + shipping`.

The result must be a JavaScript number rounded to the nearest whole Vietnamese dong, not a formatted string.

## Edge Cases and Errors

- An empty cart returns `0`, with no VAT and no shipping.
- A negative `price` throws `RangeError`.
- A `qty` that is not a positive integer throws `RangeError`.

## Worked Example

For:

- `2 * 180000 + 1 * 45000 = 405000` subtotal
- VAT of `8%` gives `32400`
- Shipping is `30000` because the subtotal is below the `500000` free-shipping threshold

The expected result is `467400`.

## Constraints

- Use plain JavaScript.
- Add no external dependencies.
- Preserve the existing public API and export.
- Do not change the assignment specification.
- Keep the implementation focused and ensure the relevant tests pass.

Do not implement behavior outside this contract. Do not modify `AI-LOG.md`, `AGENTS.md`, `src/cart.js`, or the tests while creating or reviewing this brief; implementation work may later modify only the allowed files listed above.
