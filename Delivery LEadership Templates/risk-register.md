# Risk Register

> Copy to `delivery-leadership-package/risk-register.md`. At least 5 rows. **No boilerplate**; your peers will grade you on whether these are real.

| # | Risk | Owner | Likelihood (L/M/H) | Impact (L/M/H) | Mitigation | Trigger to escalate |
|---|---|---|---|---|---|---|
| R1 |Much of the work is focused on APIs, validation, data handling and quote-generation but not accuracy of the calculations| Technical Lead| M | H | Validate output of the calculations | As soon as engineering team identifies the difference in the calculations|
| R2 | Holiday in the middle of the project week so there is a possibility that decisions can be delayed| Delivery Lead| H | M |Try to complete and save project work as much as possible and look ahead of the time regarding what decisions are needed from everyone and get the output prior to holiday| Any items that spans the holidy|
| R3 |Bad data| $0.35 quote is still in the database| Delivery lead | H |  M| Execute npm run seed before any showcase |Any showcase running before the resreset| R4 |Starter project copied incorrectly, some files are missing|  Delivery Lead|  M|  M|  Compare the project structure with the lab guide before first commit| Project files are missing from the lab folder |
| R5 | Environment setup differs between team members| Delivery Lead | M |  H| Validate environment setup using the same documented steps and versions | Environment setup is causing difficulties in project delivery |

## How I'll use this register

I will reread it each day before commit. if any new risks are identified or older risks resolved based on the progress, I will update the log. This will help me to specifically call out what actually happened during the entire project start to complete.
