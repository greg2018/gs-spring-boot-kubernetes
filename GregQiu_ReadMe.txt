# 
https://spring.io/guides/gs/spring-boot-kubernetes/

mvnw.cmd package

ls -l target/*.jar

java -jar target/demo-0.0.1-SNAPSHOT.jar

http://localhost:8080/

mvnw spring-boot:build-image


docker tag demo:0.0.1-SNAPSHOT gregqiuSpringguides/demo

 docker push gregqiu/springhellodemo
 
kubectl create deployment demo --image=gregqiu/springhellodemo --dry-run=client -o=yaml >> deployment.yaml

kubectl create service clusterip demo --tcp=8080:8080 --dry-run=client  -o=yaml >> service-deployment.yaml

kubectl apply -f deployment.yaml

kubectl apply -f service-deployment.yaml

kubectl port-forward svc/demo 8080:8080

######## Alternatively 1 rename  service-deployment.yaml to ClusterIP-service-deployment.yaml：
kubectl apply -f ClusterIP-service-deployment.yaml

kubectl port-forward svc/cluster-demo 8080:8080

###  Alternatively 1：
kubectl apply -f nodePort-service-deployment.yaml

minikube service demo --url

minikube service kubernetes --url

http://IP_ADDRESS:30001/


kubectl delete deployment demo

kubectl delete svc demo
