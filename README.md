# k8s-project
DevopsAdvancedCourse - First Project

Continuous Integration Pipeline
1) Jenkins instalation:
cd jenkins
kubectl apply -f jenkins-sa.yaml
kubectl apply -f jenkins-volume.yaml
helm install jenkins -n jenkins -f jenkins-values.yaml jenkinsci/jenkins

minikube ssh
sudo chown -R 1000:1000 /data/jenkins-volume

2) In jenkins execute ci/jenkinsFile


Continuous Deployment Pipeline
1) charts are created and stored at the /charts folder
2) CD


RabbitMQ Monitor
helm install rabbitmq bitnami/rabbitmq --set metrics.enable=true

git clone https://github.com/rabbitmq/rabbitmq-server.git
cd rabbitmq-server/deps/rabbitmq_prometheus/docker
docker-compose -f docker-compose-metrics.yml up -d
docker-compose -f docker-compose-overview.yml up -d