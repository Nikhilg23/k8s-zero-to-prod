## Nginx Deployment with ClusterIP Service

This setup demonstrates a basic Kubernetes Deployment and Service.

### Components
- **Deployment**
  - 2 replicas
  - Resource requests and limits
- **Service**
  - Type: ClusterIP
  - Internal load balancing using labels

### Key Concepts
- Pods are managed using labels and selectors
- Service provides a stable endpoint for dynamic Pods
- ClusterIP exposes the service internally within the cluster
