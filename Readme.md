## Hello word 

docker build -t hello-word:0.0.1 . --no-cache


docker run -p 8080:8080 hello-word:0.0.1


 curl -s -X GET  http://localhost:8080/api/hello | jq
{
  "message": "Hola Mundo"
}


https://docs.litmuschaos.io/docs/getting-started/installation
Mongo 
helm install my-release bitnami/mongodb --values mongo-values.yml  -n litmus --set persistence.mountPath=/data/db --version 16.3.0


helm install chaos litmuschaos/litmus --namespace=litmus \
--set portal.frontend.service.type=NodePort \
--set mongodb.image.repository=arm64v8/mongo \
--set mongodb.image.tag=latest \
--set persistence.mountPath=/data/db \
--set architecture=standalone