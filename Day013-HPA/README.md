# Day 13 – Horizontal Pod Autoscaler (HPA)

## Objective
Learn how Kubernetes automatically scales pods based on CPU utilization using Horizontal Pod Autoscaler.

## What I Implemented
- Created a Deployment with CPU requests and limits
- Configured HPA using autoscaling/v2 API
- Enabled auto-scaling based on CPU utilization

## Key Learnings
- HPA uses **resource requests**, not limits
- Scaling happens between minReplicas and maxReplicas
- Metrics-server is mandatory for HPA
- CPU utilization = actual usage / CPU request

## Files
- deployment.yaml – Application deployment with CPU requests
- hpa.yaml – Horizontal Pod Autoscaler configuration
