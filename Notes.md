## Summary of Changes

I focused on fixing issues that had the biggest impact on functionality and user experience.

1. Fixed the status filter so tasks are correctly filtered by status. The SQL query contained a logical condition issue caused by incorrect grouping of `AND` and `OR` clauses.
2. Improved search performance by removing an artificial delay in the backend controller that was slowing API responses.
3. Fixed a frontend loading-state issue where the loading indicator could remain active after a failed request. The loading state is now reset correctly for both success and error scenarios.

## What I Chose Not to Change

I did not refactor the overall architecture or redesign the UI. The goal of the exercise was to deliver focused fixes with a small, high-quality diff rather than perform a large rewrite.

I also left the current pagination implementation unchanged, although it could be optimized further by moving pagination to the database layer.

## Biggest Remaining Risk

The backend currently loads all matching tasks and performs pagination in memory. This is acceptable for the provided dataset but could become a performance bottleneck with a much larger number of records.

## AI / Tools Used

I used GenAI to help analyze the codebase, validate my understanding of the bugs, and discuss possible fixes. All code changes were reviewed, understood, tested locally, and adjusted manually before being committed.
