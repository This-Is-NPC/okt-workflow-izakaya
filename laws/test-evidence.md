---
name: Test evidence
severity: error
---
1. Ship every behavioral change with a failing-then-passing test in the same diff, or a `#tests-passing` comment containing the rerunnable command, relevant output, and duration.
2. Verify a claim about the delivered system on that real artifact under the stated condition, not only through test doubles.
3. Prove a state change through an independent read path: a new request, connection, or process, never only the write response.
4. Make a test fail by removing its guard or inverting its condition, then revert that mutation; never weaken an assertion to prove it.
