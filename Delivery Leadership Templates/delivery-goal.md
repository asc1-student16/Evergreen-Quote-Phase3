# Delivery Goal: Evergreen Quote

> Copy this file into `delivery-leadership-package/delivery-goal.md`. One sentence. Read it back to yourself. Then to your pair. Then to someone who wasn't in the room. If they can repeat it, it's good.

## Goal

Build and successfully deploy the Evergreen Quote microservice, demonstrating a complete DevOps delivery pipeline from development through testing, containerization, CI/CD, and Kubernetes deployment while meeting all sponsor and leadership requirements.

## "Done" looks like

- The API answers every documented route: list, fetch by id, create with a computed premium.
- The same data answers through GraphQL, with the explorer at `/explorer`.
- `npm test` passes; the safety net holds.
- The containerized API serves the same answers as the dev server, and the CI run on the merge commit is **green**.
- The cluster demo shows three API pods behind one Service.
- A reviewed PR is merged, branch deleted.
- `delivery-leadership-package/` is complete and committed.

## Out of scope (this week)

-User authentication, authorization, and account management.
-Advanced insurance rating algorithms beyond the sponsor-provided premium calculation logic.
-Front-end redesign or development of a new customer-facing user interface.
-Payment processing, policy issuance, or claims management functionality.
-Multi-region deployments, high-availability architecture, and disaster recovery solutions.
-Production-grade security hardening, penetration testing, and compliance certification.
-Performance optimization for large-scale production workloads.
-Monitoring, alerting, and observability platforms beyond basic deployment verification.
-Integration with external insurance carrier systems or third-party services not included in the capstone requirements.
-Migration of existing customer data from legacy systems.
-Features or enhancements not defined in the Engineering Brief, Sponsor Decisions, or project backlog.