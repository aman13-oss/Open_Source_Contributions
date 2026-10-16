# woocommerce-google-analytics-integration PR #699 — Skip Purchase Tracking for Failed and Cancelled Orders

## 1. Project Overview

**Project:** WooCommerce Google Analytics Integration

This project integrates Google Analytics tracking with WooCommerce stores to track e-commerce activities, including purchase events.

**Contribution Type:** Bug Fix

**Status:** Merged

## 2. Problem Statement

Purchase tracking should not run for orders that have failed or been cancelled.

If a failed or cancelled order triggers a purchase event, Google Analytics may record an incorrect purchase. This can lead to inaccurate e-commerce analytics.

## 3. Issue

**Issue:** #699

The goal was to prevent purchase tracking for failed and cancelled orders.

## 4. Solution Implemented

I updated the purchase-tracking logic to skip orders with failed or cancelled statuses.

The changes include:

- Skip purchase tracking for failed orders.
- Skip purchase tracking for cancelled orders.
- Avoid tracking missing orders and orders that have already been tracked.
- Add regression tests for failed and cancelled orders.
- Verify that `_ga_tracked` metadata is not set for the failed and cancelled orders covered by the tests.

Pending orders and the filter change were intentionally kept outside the scope of this PR.

## 5. Testing

- PHP lint passed.
- Unit tests were added for failed and cancelled orders.
- Unit tests could not be executed locally because the WordPress test environment was not initialized.
- The pull request passed 14 checks according to GitHub's merge summary.

**Note:** Passing PHP lint verifies syntax, but it does not replace executing the unit tests.

## 6. Code Review

The pull request was reviewed by the project maintainer.

- The maintainer approved the changes.
- No open review findings were reported.
- The maintainer confirmed that the code looked good.

Feedback received: Use the repository's pull request template for future contributions.

## 7. Merge Details

- **Pull Request:** [#700 — Skip purchase tracking for failed and cancelled orders](https://github.com/woocommerce/woocommerce-google-analytics-integration/pull/700)
- **Status:** Merged
- **Merged Into:** `woocommerce:trunk`
- **Merge Commit:** [`dc4a15b`](https://github.com/woocommerce/woocommerce-google-analytics-integration/commit/dc4a15b)

### Proof of Contribution

The pull request was approved by the project maintainer and merged into the original WooCommerce repository.

- [View the merged Pull Request](https://github.com/woocommerce/woocommerce-google-analytics-integration/pull/700)
- [View the merge commit and code changes](https://github.com/woocommerce/woocommerce-google-analytics-integration/commit/dc4a15b)

These links provide public evidence of the merged contribution and the changes included in the merge.


## 8. Skills Practiced

- PHP
- Git and GitHub
- Debugging and bug fixing
- Regression testing
- Code review
- Open-source collaboration

## 9. Key Learning

This contribution helped me practise the complete open-source workflow: understanding an issue, implementing a focused fix, adding regression tests, responding to review feedback, and getting a pull request merged.

---

*This document records my contribution and links to the original pull request. The actual source code remains in the original project repository.*
