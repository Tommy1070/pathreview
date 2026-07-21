## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/157

**Issue title:** Relevance scorer "partial overlap" test fixture actually has full query overlap

**Tier:** [x] Tier 1  [ ] Tier 2  [ ] Tier 3

**Problem summary:**
The issue is caused by a unit test that is intended to verify partial keyword overlap, but the current test data actually contains all of the query terms. Because of that, the relevance scorer correctly returns a full overlap score, causing the test to fail. The fix is to update the test fixture so it only contains some of the query words, allowing the test to accurately verify partial-overlap behavior.

**Branch name:** test/157-fix-partial-overlap-fixture

**Setup confirmation:** [x] App runs locally at localhost:5173

**Cohort ledger:**  [x] Issue added to cohort ledger