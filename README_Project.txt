Github repo: https://github.com/genesisNo04/microservices-aws-kubernetes-project-starter.git
Create docker images: 
- To create docker images user just need to make changes to the code and push to the repo. The codebuild will trigger automatically upon change and create a new image and push the image to ECR repo on aws.
After the image is created you can put the image link into the analytics-api.YAML
Create a kubernetes cluster and node group as the course has showed in the lecture
Create postgresql database with helm and check the connection, also import the seed data into the DB like  the configure section in the project (https://learn.udacity.com/nanodegrees/nd9991/parts/cd12355/lessons/d3dbdebf-df97-4fbe-a4f6-bf9a540abfda/concepts/e8cca304-7aa2-449d-9c8f-6555dbcd5596)
After that get the password of the db and put into secret.yaml file
Use command: kubectl apply -f deployment/ (navigate to project folder first) to create new pods and service for the application
Use kubectl get pods to make sure the pods is running and it is ready
Call the api end point and use kubectl logs <podname> command to check logs to see if the application is running