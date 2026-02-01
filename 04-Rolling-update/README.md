# Day 4 
focuses on observing Kubernetes rolling update behavior by updating a Deployment image and watching Pods transition without downtime.

StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  25% max unavailable, 25% max surge

**cmd** 
- kubectl apply -f deployment-name
- kubectl apply -f service-name
- kubectl get pods -n namespace-name
- kubectl get svc -n namespace-name
- kubectl get pods -n namepsace-name -w [w is watch mode ] its help to show the pods behavior 