# Cosmocloud Deploy

This is a Helm chart for deploying a three-tier application consisting of Frontend, Backend, and Redis components.

## Components

- **Frontend**: React application exposed via NodePort

  - Image: shreybatra/sample-frontend
  - Port: 5173
  - NodePort: 31000

- **Backend**: FastAPI application

  - Image: shreybatra/sample-backend
  - Port: 8000
  - Service Type: ClusterIP

- **Redis**: Cache storage
  - Image: redis
  - Port: 6379
  - Service Type: ClusterIP

## Prerequisites

- Kubernetes cluster (version 1.19+)
- Helm 3.0+

## Installation

To install the chart:
`helm install testapp cosmocloud-deploy --atomic --timeout 30s`

## Verification

After installation, verify the deployment using:

```bash
# Check running pods
kubectl get pods

# Check services
kubectl get services
```

## Notes

- The frontend service is exposed via NodePort for external access

- Backend and Redis services use ClusterIP for internal communication

- All components are deployed with single replicas as per requirements
