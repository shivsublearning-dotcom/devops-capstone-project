---
name: User Story
about: A user story to be completed in a sprint
title: ''
labels: ''
assignees: ''
---

**As a** [role]
**I need** [function]
**So that** [benefit]

### Details and Assumptions
* [document what you know]

### Acceptance Criteria
```gherkin
Given [some context]
When [certain action is taken]
Then [the outcome of action is observed]
```
Evidence (Option 1): URL of `user-story.md`. Option 2: screenshot `planning-storytemplate-done.png`.

## Ex 4 – Seven stories (create via New issue → User Story; add each to the board's New issues column)

| # | Title | As a / I need / So that | Acceptance (Given/When/Then) |
|---|---|---|---|
| 1 | Set up the development environment | developer / a working dev environment with Python, Flask, DB and tests / I can develop and test the service | Given a fresh clone, When I run the setup steps and `make test`, Then dependencies install and existing tests pass |
| 2 | Read an account from the service | service consumer / `GET /accounts/{id}` / I can view a customer's details | Given account 1 exists, When I GET /accounts/1, Then I get 200 and its JSON; Given it doesn't exist, Then 404 |
| 3 | Update an account in the service | service consumer / `PUT /accounts/{id}` / I can correct a customer's name or address | Given account 1 exists, When I PUT valid data, Then 200 and the changes persist; unknown id → 404 |
| 4 | Delete an account from the service | service consumer / `DELETE /accounts/{id}` / I can remove a customer | Given account 1 exists, When I DELETE it, Then 204 and a following GET returns 404 |
| 5 | List all accounts in the service | service consumer / `GET /accounts` / I can see all customers | Given 3 accounts exist, When I GET /accounts, Then 200 and a list of 3; none → 200 and `[]` |
| 6 | Containerize your microservice using Docker | DevOps engineer / a Dockerfile / the service runs the same everywhere | Given the Dockerfile, When I `docker build` and `docker run`, Then the service answers on its port |
| 7 | Deploy your Docker image to Kubernetes | DevOps engineer / K8s manifests / the service runs scaled and managed in a cluster | Given the image in a registry, When I `kubectl apply`, Then pods are Running and the service is reachable |

Evidence: screenshot `planning-userstories-done.png` (all 7 under New issues).

## Ex 5 – Triage
Move stories **1–5 → Product backlog**; **6 and 7 → Icebox**. Screenshot `planning-productbacklog-done.png`.

## Ex 6 – Refine
- Labels → New label: `technical debt`, color yellow (e.g. `#FBCA04`).
- `enhancement` on stories 2, 3, 4, 5 (customer value); `technical debt` on story 1 (and 6, 7 if you like).
- Rank top→bottom: 1 Setup env, 5 List, 2 Read, 3 Update, 4 Delete (setup first; list/read are the simplest customer-visible wins; the order of 2–5 is a judgement call you can justify).
- Show the Labels field in the board view (Fields → Labels). Screenshot `planning-labels-done.png`.

## Ex 7 – Sprint
- Project → Settings → Iteration field: create Sprint 1, 2, 3, 1 week each.
- Estimates (story points field, scale 3/5/8/13): 1 Setup = 5, List = 3, Read = 3, Update = 5, Delete = 3 (adjust as you see fit).
- Assign each of the five to **Sprint 1**, move to **Sprint backlog** keeping the ranked order (the lab says to close each issue as you go – follow that).
- Checklist: every story has a label, an estimate, and Sprint 1.
- Screenshot `planning-kanban-done.png`.

Screenshots on Windows: `Win + Shift + S`, save as PNG. Submit the repo URL and screenshots in the Capstone final project (AI-graded or peer-graded).
