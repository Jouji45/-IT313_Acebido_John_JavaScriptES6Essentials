# -IT313_Acebido_John_JavaScriptES6Essentials

## Problem
The registrar provided a raw list of enrollee records, each with prelim, midterm, and final scores.
This program processes that data into a formatted eligibility report. An enrollee is PASSING if the
average of their three scores is 75 or above; otherwise they are on PROBATION. The report also shows
the class average and how many students are passing.

## Approach
- Created a separate module, `gradeUtils.js`, using ES module `export`/`import` syntax:
  - `computeAverage(prelim, midterm, final)` — a named export that returns the average of the three scores.
  - `isPassing(average)` — a default export that returns true if the average is 75 or above.
- Simulated fetching enrollee data from a registrar API using `getEnrollees()`, which returns a Promise
  that resolves the enrollee array after a short delay (via `setTimeout`).
- Used `async`/`await` inside a `try/catch` block in `main()` to safely handle the simulated fetch,
  so a failed "connection" is caught and logged instead of crashing the program.
- Used destructuring to pull `name`, `prelim`, `midterm`, and `final` out of each enrollee record.
- Used `.map()` with the imported functions to transform raw records into `{ name, average, status }` objects.
- Used `.filter()` to separate passing enrollees from those on probation.
- Used `.reduce()` to compute the overall class average.
- Used template literals to format and print the final report.

## How to Run
1. Make sure [Node.js](https://nodejs.org/) is installed.
2. Clone this repository and open it in your terminal.
3. Run:
   \`\`\`
   node main.js
   \`\`\`
4. The eligibility report will print to the console.

## Files
- `gradeUtils.js` — grade calculation module (named + default exports)
- `main.js` — main script (data, simulated fetch, async/await, array processing, report output)