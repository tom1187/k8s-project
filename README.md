# k8s-project
DevopsAdvancedCourse - First Project

### Continuous Integration Pipeline
1) Jenkins instalation:
cd jenkins
kubectl apply -f jenkins-sa.yaml
kubectl apply -f jenkins-volume.yaml
helm install jenkins -n jenkins -f jenkins-values.yaml jenkinsci/jenkins
kubectl create clusterrolebinding jenkins --clusterrole cluster-admin --serviceaccount=jenkins:default

<img width="1390" alt="image" src="https://user-images.githubusercontent.com/54473916/178986544-8b7fd8f7-15f3-45b3-8aef-b25d9b2f8996.png">

minikube ssh
sudo chown -R 1000:1000 /data/jenkins-volume

2) In jenkins execute ci/jenkinsFile
<img width="525" alt="image" src="https://user-images.githubusercontent.com/54473916/178986790-af50253b-31e0-4669-a7b8-a0aae5202ef3.png">
<img width="429" alt="image" src="https://user-images.githubusercontent.com/54473916/178986858-8887dc3d-60d9-4e33-8d47-7996dc528199.png">


### Continuous Deployment Pipeline
1) charts are created and stored at the /charts folder
2) In jenkins execute cג/jenkinsFile
<img width="1345" alt="image" src="https://user-images.githubusercontent.com/54473916/178986670-b43dc45a-9b01-455d-b7d0-177adaf734c6.png">
<img width="465" alt="image" src="https://user-images.githubusercontent.com/54473916/178988013-74c45460-0488-4f9b-84d9-40750daa1e8e.png">


### RabbitMQ Monitor
helm install rabbitmq bitnami/rabbitmq --set metrics.enable=true

git clone https://github.com/rabbitmq/rabbitmq-server.git
cd rabbitmq-server/deps/rabbitmq_prometheus/docker
docker-compose -f docker-compose-metrics.yml up -d
docker-compose -f docker-compose-overview.yml up -d

<img width="1226" alt="image" src="https://user-images.githubusercontent.com/54473916/178987839-1b06b342-073e-4900-bbd0-3920e1d990bb.png">
![image](https://user-images.githubusercontent.com/54473916/178987886-c232165d-ab34-44ff-8a56-ff122418318b.png)

