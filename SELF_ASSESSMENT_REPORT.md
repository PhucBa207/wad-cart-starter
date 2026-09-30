# Self-Assessment Report

| Criterion | Claimed mark | Evidence | Short justification |
|---|---:|---|---|
| Behaviour | 30/30 | `src/cart.js`; `test/cart.test.js` tests `the example from the slides`, `an empty cart returns zero without shipping or VAT`, `shipping is free at the threshold`, `a negative price throws RangeError`, and `a non-integer quantity throws RangeError` | The implementation calculates subtotal, VAT, threshold shipping, and whole-number rounding; it returns zero for an empty cart and throws `RangeError` for both specified invalid inputs. The worked example returns `467400`. |
| Tests | 20/20 | `test/cart.test.js`; final `npm test` result recorded in `AI-LOG.md` as five passing tests | The suite covers the worked example, empty cart, exact free-shipping threshold, negative price, and non-integer quantity. The existing test was preserved and each added edge case has a focused assertion. |
| Harness | 18/20 | `AGENTS.md` sections `Stack`, `Commands`, and `Never`; `package.json` `lint` script; `.github/workflows/ci.yml` push trigger and required npm steps | The repository has plain-JavaScript/npm rules, explicit `Never` rules, a working `npm test` and `npm run lint` gate, and a push-triggered GitHub Actions workflow. I deducted conservatively because `AGENTS.md` does not explicitly list the `npm run lint` command in its commands block, and the hosted workflow was not observed running remotely. |
| Brief | 15/15 | `BRIEF.md` sections `Goal`, `Files and Scope`, `Contract`, `Edge Cases and Errors`, `Worked Example`, and `Constraints` | The brief identifies the allowed files, implementation location, full contract, required errors, no-dependency constraint, and worked result clearly enough for another person to reproduce the intended implementation. |
| AI-LOG.md | 15/15 | `AI-LOG.md` sections `AI Tool Used`, `What Copilot Produced`, `Changes Accepted`, `Rejected Changes or Suggestions`, `Manual Work`, and `Evidence and Checks` | The log identifies GitHub Copilot, records the produced files and accepted implementation, states that no suggestions were rejected, describes manual review and commands, and records the observed red and green test results. |

**Total claimed mark: 98/100**

## What I did not manage

I did not verify the GitHub Actions workflow on a remote push, and there is no separate test specifically asserting fractional-total rounding; the implementation uses `Math.round` as required.
