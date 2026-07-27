## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/157

**Issue title:** Relevance scorer "partial overlap" test fixture actually has full query overlap

**Tier:** [x] Tier 1  [ ] Tier 2  [ ] Tier 3

**Problem summary:**
The issue is caused by a unit test that is intended to verify partial keyword overlap, but the current test data actually contains all of the query terms. Because of that, the relevance scorer correctly returns a full overlap score, causing the test to fail. The fix is to update the test fixture so it only contains some of the query words, allowing the test to accurately verify partial-overlap behavior.

**Branch name:** test/157-fix-partial-overlap-fixture

**Setup confirmation:** [x] App runs locally at localhost:5173

**Cohort ledger:**  [x] Issue added to cohort ledger
## Week 8 — Reproduction & solution planning

**Reproduction commit link:** [Add after committing and pushing]

**Reproduction summary:**
I reproduced the issue by running `pytest tests/unit/test_relevance_scorer.py -q`. The `test_query_with_partial_overlap` test failed because the query `"Python Django web framework"` and the test chunk share all four query terms, causing the relevance scorer to return `1.0` instead of the expected partial-overlap range of `0.3` to `0.9`.

**PLAN.md link:** [Add after creating and pushing PLAN.md]

**Walkthrough video (recommended):** Not recorded

**Blockers or open questions:**
I still need to determine which query term should be removed or replaced so the test represents meaningful partial overlap while remaining different from the full-overlap and zero-overlap tests.
