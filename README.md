## Github Repo:

 [Link to Github repo](`https://github.com/HungParfait/cd12355-microservices-aws-kubernetes-project-starter`)
## How to deploy:
- Step 1: Create K8s cluster with eksctl, all configuration written in `cluster.yaml` file.

    `eksctl create cluster -f cluster.yaml`
- Step 2: Install Helm Postgres Chart into cluster.

    `helm repo add bitnami https://charts.bitnami.com/bitnami`

    `helm install bitnami/postgresql --generate-name`
- Step 3: Apply configMap, secret, application deployment, application service into cluster
    
    `kubectl apply -f ./deployment/configMap.yaml`

    `kubectl apply -f ./deployment/secrets.yaml`

    `kubectl apply -f ./deployment/deployment.yaml`

    `kubectl apply -f ./deployment/service.yaml`
- Step 4: Verify whether our application working or not by running port-forward command and test.

    `kubectl port-forward --namespace default svc/my-service  80:80`

    `kubectl port-forward --namespace default svc/postgresql-1689951514  5432:5432`

Now, our application is exposed to port 80, localhost so we can easily test it.