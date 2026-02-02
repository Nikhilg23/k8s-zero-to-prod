# Day 5 

focuses on controlling rolling updates using maxSurge and maxUnavailable to safely manage pod availability during deployments.

**Lock this mental model (simple & correct)**
- replicas = 3 → what you want finally
- maxSurge = 1 → extra pod allowed temporarily
- maxUnavailable = 1 → only 1 pod can be down at a time

**So during update:**
- 3 (running) + 1 (temporary) = 4 pods