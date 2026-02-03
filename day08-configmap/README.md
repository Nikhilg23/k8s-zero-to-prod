# Day 8 – ConfigMaps

Learned how to use Kubernetes ConfigMaps to externalize application configuration and inject values into pods using environment variables without rebuilding container images.

**windows powershell cmd**
- kubectl exec -it [pod-name] -n dev-1 -- env | Select-String APP_

**linux Cmd**
- kubectl exec -it [pod-name] -n dev-1 -- env | grep APP_

Or you can run with --

- kubectl exec -it [pod-name] -n dev-1 -- sh
- env | grep APP_

