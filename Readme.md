# Note
- kubernetes doesnot check whether credentials are correct or not(username or password), pods will run but the authentication with service will fail 
- error obtained can be:
    `Authentication failed` or `failed to connect to database`

# Quick Start with k8s

# step 1: configure secret
- make saperate files
- use appropriate naming convention like mongo-secrets.yaml

# step 2: confif file (using configMap)
- The movement we deploy mongodb and deploy it as a service, then we will get the url(in this case - mongodb)

# step 3: write development controller (in this project - mongo-app.yaml)

# step 4: Prepare for development 
- check for image name:tag, naming convention...

# step 5: create service
- Do take care of connecting deployment and service (using: selector->applabel->app)    

-----------------------------------------
# why we create webapp
- Reason: mongo is a database and we cannot interact with it directly, it stores data. To interact with it, we need webapp which will handle req/res and required actions. 

------------------------------------------
# creating resources || deploying kubernetes app (steps)
- Dump secrets and configs: `kubectl apply -f webapp.yaml`
- ...same for all files (sequence: mongo-secret, mongo-config, mongo-app, mongo-service, webapp)

- check whether pods are running or not `kubectl get pods`

- some commands to run on pods
`kubectl get secret`
`kubectl get configMap`
`kubectl get svc` - get all services

`minikube ip` - minikube running ip address
- our app is running on port 8081 but we cannot explore it directly using ip,
 we need to mention service
`minikube service webapp-service`
