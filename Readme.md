# Lab: Test Planning and Defect Management

## Topics

- Test planning
- Test case design
- Test execution
- Defect reporting
- Confirmation testing

## Learning Objectives

- Create a test plan for a small application.
- Define test objectives, scope, risks, and entry and exit criteria.
- Design and execute test cases.
- Compare expected and actual results.
- Write a reproducible defect report.

# Deliverables

## Step 1: Create a Test Plan

Create a brief test plan for the provided Counter application.

Include:

- Test objectives
- What is in and out of scope
- The testing approach
- The test environment and tools
- At least one product risk
- Entry and exit criteria

## Step 1: Test Plan

**Test objectives:** Verify that the Counter application displays the correct count and that the Increment, Decrement and Reset buttons change it as expected.

**In scope:** The displayed count, the starting value, and the behavior of the three buttons, including sequences of button clicks.

**Out of scope:** Visual styling, performance, accessibility, browser compatibility, and automated tests.

**Testing approach:** Manual, black box testing of the running application. I will design test cases from the expected behavior of the buttons, execute them by hand, and record the results. Any failure will be repeated to see whether it can be reproduced.

**Test environment and tools:** Windows, Google Chrome 157.0.8103.80, the app running locally with `npm run dev` at `http://localhost:5173`, a text editor for notes, and Git and GitHub for submission.

**Product risk:** A button might change the count in the wrong way, such as the wrong direction, so users would see incorrect counts without any warning.

**Entry criteria:** The application builds and runs locally, and the test cases are written.

**Exit criteria:** All test cases have been executed, results are recorded, and every failure has been repeated and reported.

## Step 2: Design Test Cases

Create at least four test cases for the application.

For each test case, include:

- Test case ID
- Starting state
- Actions
- Expected result

At least one test case should involve multiple actions in sequence.

### My Test Cases

| Test Case ID | Starting State | Actions | Expected Result |
| ------------ | -------------- | ------- | --------------- |
| TC-01 | The app has just loaded | None; look at the page | The page shows "Count: 0" and the Increment, Decrement and Reset buttons |
| TC-02 | Count is 0 | Click Increment once | The count shows 1 |
| TC-03 | Count is 0 | Click Decrement once | The count shows -1 |
| TC-04 | Count is 3 (after clicking Increment three times) | Click Reset | The count shows 0 |
| TC-05 | Count is 0 | Click Increment twice, click Decrement once, click Increment once, click Reset, click Increment once | After each click the count shows 1, 2, 1, 2, 0, 1 |

## Step 3: Execute the Tests

Run your test cases against the application.

For each test case, record:

- Actual result
- Pass or fail

Repeat any failed test to determine whether the result can be reproduced.

### My Test Results

| Test Case ID | Actual Result | Pass or Fail | Notes |
| ------------ | ------------- | ------------ | ----- |
| TC-01 | The page showed "Count: 0" and the Increment, Decrement and Reset buttons | Pass | |
| TC-02 | The count changed from 0 to 1 | Pass | |
| TC-03 | The count changed from 0 to 1 instead of -1 | Fail | Repeated a second time and got the same result, so it is reproducible |
| TC-04 | The count changed from 3 to 0 | Pass | |
| TC-05 | After the Decrement click the count went up instead of down (1, 2, 3, 4, 0, 1 instead of 1, 2, 1, 2, 0, 1) | Fail | Repeated a second time and got the same result, so it is reproducible |

## Step 4: Report a Defect

If you find a defect, create one defect report.

Include:

- Defect ID and title
- Related test case
- Test environment
- Steps to reproduce
- Expected result
- Actual result
- Severity and priority
- Status

If none of your tests fail, state that you did not find a defect and identify the tests you performed.

### My Defect Report

| Field | Information |
| ----- | ----------- |
| Defect ID | DEF-001 |
| Title | Decrement button increases the count instead of decreasing it |
| Related Test Case | TC-03 and TC-05 |
| Test Environment | Windows, Google Chrome 157.0.8103.80, Counter app running locally with `npm run dev` at `http://localhost:5173` |
| Steps to Reproduce | 1. Open `http://localhost:5173`. 2. Confirm the page shows "Count: 0". 3. Click the **Decrement** button once. |
| Expected Result | The count decreases by one and shows "Count: -1". |
| Actual Result | The count increases by one and shows "Count: 1". Clicking Decrement again keeps raising the count. The failure happened every time I repeated it. |
| Severity | High |
| Priority | High |
| Status | New |

## What to Submit

1. Create and initialize a GitHub repository.
2. Commit and push your work to the repository.
3. Make sure the repository is public. Private repositories will not receive credit.
4. Submit the URL on canvas

## AI Transparency

AI was used to clean up this file.
