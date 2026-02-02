# Day 5 – Controlled Rolling Updates

This module focuses on **controlling Kubernetes rolling updates** using
`maxSurge` and `maxUnavailable`.

## 🎯 Goal
To understand how Kubernetes controls pod availability and rollout speed
during a Deployment update.

## 🧱 What was done
- Used an existing Deployment with 3 replicas
- Configured rolling update strategy:
  - `maxSurge: 1`
  - `maxUnavailable: 1`
- Updated the container image to trigger a rollout
- Observed pod behavior during the update

## 👀 Observations
- Total pods increased temporarily from **3 to 4**
- Only **one pod** was unavailable at any time
- Old and new pods coexisted during the update
- After completion, the Deployment returned to **3 replicas**

## 🧠 Key Learnings
- `maxSurge` controls how many **extra pods** can be created temporarily
- `maxUnavailable` controls how many pods can be **down** during an update
- Rolling updates can be **safely controlled** to avoid downtime

## ✅ Outcome
After Day 5, I can control how Kubernetes performs rolling updates and
ensure application availability during deployments.
