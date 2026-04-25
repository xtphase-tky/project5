# Architecture Overview

The architecture emphasizes on always validating a PR and safely deploying to development cloud server using Github actions workflows

## Flow

Pull request → PR Validation (ci) → merge and push event → Build image and push to ECR → Deploy to dev EC2 → Smoke test

---

## Components

### 1. Activation of CI

- CI gets initated everytime a PR becomes relevant to the main branch

### 2. Lint and format tests

- CI tests the PR for lint errors
- CI also tests prettier format mistakes and typescript errors

### 3. Unit and Integration Tests

- CI performs all unit and integration from package-lock.json for PR validation

### 4. Build Check

- CI performs a build check at end of pipeline

### 5. Activation of CD to dev server

- Pipeline gets initiated on push events to dev branch

### 6. Build and Push

- CD pipeline builds docker image and pushes to ECR

### 7. Deploy to EC2

- CD uses SSH to safely deploy to development EC2 server

### 8. Smoke test

- CD pipeline performs a smoke test to verify development server's health

---
