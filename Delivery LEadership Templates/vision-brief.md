# Evergreen Quote: Vision Brief

> Copy this file into `delivery-leadership-package/vision-brief.md` in your repo and fill it in. Target length: 1 page (~300 words). Write for a Liberty Mutual VP who has 90 seconds.

## Product
**Name:** Evergreen Quote API (Phase 3 service delivery)
**Delivery week:** 3
**Delivery Lead:** Yamini Dumpala
**Engineering team (represented by):** _link to your Evergreen Quote project repo_
**GitHub Project board:** _link_

## Who is the customer?
Evergreen Quote serves three primary customer groups. First, the digital experience team needs a rEeliable backend service that can create, store, and retrieve insurance quotes instead of relying on calculations performed only in a web page. Second, partner organizations and future integrations need a standard API that allows them to access quote information without duplicating business logic. Third, the operations team needs a solution that can be tested automatically, packaged consistently, and deployed to Kubernetes so it can be supported in production. Till now, quote information is generated but not managed as a reusable service, making it difficult for other teams and channels to benefit from it.
## What pain does Evergreen Quote remove?
The biggest pain is that quote information is temporary and difficult to reuse. A customer may receive a quote, but there is no centralized service that reliably stores and retrieves that information later. Evergreen Quote creates a single source of truth for quote data so that the website, partners, and future applications all receive consistent results. The service also improves quality by validating input before data is saved, reducing errors and bad records. From an operational perspective, automated testing, containerization, and Kubernetes deployment reduce the risk of configuration differences and failed releases.

## What does "good" look like at end of the week?

-The quote service successfully creates, stores, and retrieves insurance quotes through the REST API.
-Invalid quote submissions are rejected with meaningful validation messages before reaching the database.
-GraphQL queries and mutations provide the same information available through the REST endpoints.
-MongoDB is integrated and storing quote data correctly.
-Automated tests pass locally and in GitHub Actions on every code change.
-Sponsor-requested business rules and premium rates are implemented and verified.
-Docker containers build successfully and behave consistently across environments.
-Kubernetes deployments run successfully with healthy pods servicing application requests.
-Project risks, key decisions, status updates, and the final go/no-go recommendation are documented and ready for stakeholder review.
-The final demonstration shows a working application, automated delivery pipeline, and successful deployment to the target platform.
## What are we explicitly NOT doing this week?
-Building authentication, login functionality, or user account management.
-Developing a sophisticated insurance rating engine beyond the provided business requirements.
-Creating new product features that are not part of the capstone scope.
-Replacing required technologies such as MongoDB, GraphQL, Docker, GitHub Actions, or Kubernetes.
-Implementing enterprise-scale optimizations such as multi-region deployments, advanced security controls, or disaster recovery solutions.
-Performing extensive user interface redesign work.
-Building a fully production-ready insurance platform. The goal is to demonstrate a working service and delivery pipeline.
- 

## How will we know if it worked?
-All required REST and GraphQL functionality operates as described in the engineering requirements.
-Automated test execution reports a 100% passing rate in the CI pipeline before release.
-Quote data can be successfully created, retrieved, and validated through the application APIs.
-Docker and Kubernetes deployments produce the same behavior as the local development environment.
-Leadership deliverables are completed and reviewed.
-Stakeholders can observe a successful end-to-end demonstration showing development, testing, deployment, and operation of the Evergreen Quote service.

- 
- 
