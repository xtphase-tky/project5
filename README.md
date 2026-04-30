# YAML pipelines for PR validation and Deployment to Development Server using Github Actions Workflows

## Overview

This project enforces a strict validation check on every PR and builds, pushes docker image to registry and deploys it to Development server.

It enforces principles such as :
1. Initiation on all types of PR
2. Linting and Testing
3. Build check
4. Pushing image to ECR
5. Deployment to Dev server and smoke test 

---

## Problem Statement

Typical pipelines may have some issues like :
1. Activated only when PR is opened 
2. Waste of CI compute
3. Incorrect order of validation
4. No health checks

---

## Solution

A pipeline system that :
1. Activates everytime a PR becomes relevant
2. Has correct order of PR validation 
3. Smoke tests health endpoint
4. Uses same image for deployment as the one built and pushed
5. Manual as well as automatic initiation of CD

---

## Architecture

Pull request → PR Validation (ci) → merge and push event → Build image and push to ECR → Deploy to dev EC2 → Smoke test

See /docs/architecture.md for detailed breakdown

---

## Tech Stack

1. GitHub Actions (YAML Pipelines)
2. AWS (EC2, ECR)
3. Docker (compose, image)

---

## Key Components

### PR Validation
1. Lint Check
2. Format Check
3. Typescript Check
4. Unit tests
5. Integration Tests
6. Build check

### Deployment to Dev
1. Image Building
2. Image Pushing to ECR
3. Deployment
4. Smoke test

---

## Activation 

CI : 
 - All types of pull requests

CD : 
 - Push event to main branch
 - Through GitHub UI (Workflow dispatch present)
