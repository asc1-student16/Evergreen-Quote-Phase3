*Date:** November 10, 2026
**Author:** Yamini Dumpala
**Decision area:** Day 3 Copilot test

## What is input & Output

Copilot followed my prompt as provided: draft one more test: "a POST to /api/quote with a missing field (no coverageAmount) returns 400." It has generated a new test in the "api.test.mjs" as 

test("POST /api/quote with a missing field (no coverageAmount) returns 400", async () => {
  const res = await fetch(`${base}/api/quote`, {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({ type: "home", age: 40 }),
  });
  assert.equal(res.status, 400);
});


## Critique, what did copilot get right?what did it get wring? would you ship it as-is?
Copilot produced output is correct. The tests increased from 7 to 8 as passed. It is checking the status code as live. The test is not able to recognize that coverageAmount is missing. I will ship it as is. I have not changed any of the Copilot's output as the scope of the project for this week is just assembling the code.
## what in your pipeline checks Copilot's output?
CI confirms that Copilot's test passes, but not that it's effective; a false green looks identical to a true one. Intentionally breaking the test twice proved its validity. The pipeline may execute AI-authored code and tests, but verifying that a test is genuinely worth trusting remains a human responsibility.