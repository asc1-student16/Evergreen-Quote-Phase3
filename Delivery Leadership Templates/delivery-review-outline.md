# Delivery Review: Evergreen Quote

> Copy to `delivery-leadership-package/delivery-review-outline.md`. Five slides OR one page. Target: 5 minutes spoken, then 3 minutes of questions.

## Slide 1: Delivery goal & did we hit it?

- Goal (one sentence): Build and successfully deploy the Evergreen Quote microservice, demonstrating a complete DevOps delivery pipeline from development through testing, containerization, CI/CD, and Kubernetes deployment while meeting all sponsor and leadership requirements.
- Hit? Partially
- One-line: We have completed all the planned work but due to external team's dependency (inject # 3), main is red so the deployment is a No-Go

## Slide 2: What shipped
http://localhost:3000/
{"message":"Evergreen Quote API","status":"ok"}

http://localhost:3000/api/quotes/q1
{
  "_id": "q1",
  "type": "auto",
  "age": 41,
  "coverageAmount": 50000,
  "monthlyPremium": 96,
  "tags": [
    "renewal"
  ],
  "__v": 0,
  "createdAt": "2026-11-09T16:23:15.895Z",
  "updatedAt": "2026-11-09T16:23:15.895Z"
}


- A curl transcript or screenshot of the running Evergreen Quote API on `main`: the health route and one quote response.
-labadmin@ip-172-16-181-183:~/Phase 3 capstone/EverGreen_Phase3$ kubectl get pods
NAME                                   READY   STATUS    RESTARTS   AGE
evergreen-quote-api-578cd94ff8-92px5   1/1     Running   0          2m13s
evergreen-quote-api-578cd94ff8-sjtpf   1/1     Running   0          2m13s
evergreen-quote-api-578cd94ff8-szsdg   1/1     Running   0          2m13s
mongo-77984b56bb-4nshz                 1/1     Running   0          3m22s
labadmin@ip-172-16-181-183:~/Phase 3 capstone/EverGreen_Phase3$ kubectl get pods
NAME                                   READY   STATUS    RESTARTS   AGE
evergreen-quote-api-578cd94ff8-92px5   1/1     Running   0          4m36s
evergreen-quote-api-578cd94ff8-sjtpf   1/1     Running   0          4m36s
evergreen-quote-api-578cd94ff8-szsdg   1/1     Running   0          4m36s
mongo-77984b56bb-4nshz                 1/1     Running   0          5m45s
labadmin@ip-172-16-181-183:~/Phase 3 capstone/EverGreen_Phase3$ kubectl port-forward svc/evergreen-quote-api 8080:80
Forwarding from 127.0.0.1:8080 -> 3000
Forwarding from [::1]:8080 -> 3000
Handling connection for 8080
Handling connection for 8080
Handling connection for 8080
Handling connection for 8080
Handling connection for 8080
Handling connection for 8080
Handling connection for 8080

labadmin@ip-172-16-181-183:~$ curl localhost:8080/api/quotes
[]labadmin@ip-172-16-181-183:~curl -X POST localhost:8080/api/quote \ \
  -H "Content-Type: application/json" \
  -d '{"type":"home","age":45,"coverageAmount":200000}'
labadmin@ip-172-16-181-183:~$ curl localhost:8080/api/quotes
[{"_id":"05e49274-d07a-48f6-ae3e-eb1d81e65f92","type":"home","age":45,"coverageAmount":200000,"monthlyPremium":2700,"tags":[],"createdAt":"2026-11-12T17:01:29.629Z","updatedAt":"2026-11-12T17:01:29.629Z","__v":0}]labadmin@ip-172-16-181-183:~$ curl -X POST localhost:8080curl -X POST localhost:8080/api/quote \ \
  -H "Content-Type: application/json" \
  -d '{"type":"home","age":45,"coverageAmount":100000}'
{"type":"home","age":45,"coverageAmount":100000,"monthlyPremium":1350,"tags":[],"_id":"52c75ad7-0417-4edc-afa9-9ddfe31ab0c9","createdAt":"2026-11-12T17:02:34.237Z","updatedAt":"2026-11-12T17:02:34.237Z","__v":0}curl: (3) URL using bad/illegal format or missing URL
labadmin@ip-172-16-181-183:~$ curl localhost:8080/api/quotes
[{"_id":"05e49274-d07a-48f6-ae3e-eb1d81e65f92","type":"home","age":45,"coverageAmount":200000,"monthlyPremium":2700,"tags":[],"createdAt":"2026-11-12T17:01:29.629Z","updatedAt":"2026-11-12T17:01:29.629Z","__v":0},{"_id":"52c75ad7-0417-4edc-afa9-9ddfe31ab0c9","type":"home"
- Link to the green CI run (install from the lock file + tests against a throwaway database).
https://github.com/asc1-student16/Evergreen-Quote-Phase3/actions/runs/42858435025
## Slide 3: Two key decisions

- **Decision 1:** Renters coverage is deferred to next sprint- "Just adding one more drop down" is not that simple. All the integrations and rate decisions need to be made upfront for the drop down to be functional.
- **Decision 2:** Holding the code merge to main until Thursday as the main is red. This will allow us to get the external dependency status and make the decision of go or no-go


## Slide 4: Risks & injects

- Top risk we tracked: _from risk-register.md._
- Inject #1 (Tue): A renters request from the stakeholders which will impact the scope of the project delivery and lot of integration, data points need to be implemented. This will impact the quality of the project if becomes in scope for the project. The scope change has been deferred to next sprint.

- Inject #2 (Wed):The main is red which impacted the delivery of the project. The decision is made as a "No-Go"

## Slide 5: What I'd do differently next round

- I have not added a delivery branch and instead, I have updated my code directly into the main branch. This is very risky. In the real world where multiple team members are using the code, integrating their code with mine, this is not a suitable solution. For next round, I will definetly push the code to the delivery lead branch and then open PR & merge to the main branch.
- Check all the environments for their dependencies before each step.I have missed few dependencies which caused issues that took some time for me to understand the root cause of the issue.

## Q&A prep: likely questions

- _e.g., "Why didn't you ship X?"_
- _e.g., "The demo returned quotes all week; why does one red test matter?"_
