# Task1

1. Created two Laravel projects: app1 and app1 **

2. Build Docker images and push them to Docker Hub by running the following command: **

```
app1
docker build -t <docker_id>/<image_name> -f app1/build/Dockerfile .
docker push <docker_id>/<image_name>

app2
docker build -t <docker_id>/<image_name> -f app2/build/Dockerfile .
docker push <docker_id>/<image_name>:<tag>
```

3. Deploy laravel applications in kubernetes using minikube by following these easy steps

```
$ minikube start
$ kubectl apply -f app1/deploy/app1-deployment.yaml
$ kubectl apply -f app1/deploy/app1-configmap.yaml
$ kubectl apply -f app1/deploy/app1-service.yaml

$ kubectl apply -f app2/deploy/app2-deployment.yaml
$ kubectl apply -f app2/deploy/app2-configmap.yaml
$ kubectl apply -f app2/deploy/app2-service.yaml

$ kubectl apply -f nginx/deploy/nginx-deployment.yaml
$ kubectl apply -f nginx/deploy/nginx-configmap.yaml
$ kubectl get pods
```

Also, don't forget to replace your-docker-id and image-name in app1.deployment.yaml and app2.deployment.yaml files

4. Create a Docker Compose file that runs a Jenkins container. Create two Jenkinsfiles, one for each app, that builds and deploys the apps into the Kubernetes cluster. The Jenkinsfiles should use the Docker images built by the Jenkins pipeline. Don't forget to replace the <your-docker-id>, <image-name>, $DOCKERUSER and $DOCKERPASSWORD given in the Jenkinsfiles in app1 and app2 folders. Then run the following command:

```
docker-compose up -d
```
