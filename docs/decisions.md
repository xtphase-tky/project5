# Desicions

## Design Decisions

### 1. CI Initiation

Decision: CI is set to initiate on all types of PR
Reason: Ensures that all PR pass through validation before getting merged to main branch

### 2. CI Permissions:

Decision: CI is explicitly granted permissions to read repo
Reason: Ensures CI can access the repo without making any changes to it while ability to write to PR is allowed

### 3. Lint Check:

Decision: CI checks for linting, formatting and typescript inconsistencies
Reason: Ensures PR doesn't contain formatting errors while allowing it to pass minor llinting mistakes

### 4. Build Check

Decision: Build check happens after linting and testing checks
Reason: Building compute is not wasted if pipeline fails prior testings

### 5. Workflow dispatch

Decision: Workflow dispatch is added
Reason: CD to dev can be initated through Github UI as well

### 6. Docker Compose

Decision: Docker compose strategy is used over docker run or artifact build
Reason: Docker compose provides multi container running, env configuration, built in networking

---
