### Setup
1. Set up a Postgres database with a Helm Chart
    helm install app-db oci://registry-1.docker.io/bitnamicharts/postgresql \
    -f postgres-value.yaml \
    -n default
 
2. Create a `Dockerfile` for the Python application. Use a base image that is Python-based
 
3. Write a simple build pipeline with AWS CodeBuild to build and push a Docker image into AWS ECR
 
4. Create/Update a service and deployment using Kubernetes configuration files to deploy the application
    kubectl -ndefault apply -f configmap.yaml
    kubectl -ndefault apply -f secret.yaml
    kubectl -ndefault apply -f db.yaml
    kubectl -ndefault apply -f admin-api.yaml
 
5. Check AWS CloudWatch for application logs