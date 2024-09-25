# listar api version
kubectl api-resources
# Criar pod
kubectl apply -f meuprimeiropod.yaml
# listar pod
kubectl get pods
# saber mais detalhes do pod
kubectl describe pod meuprimeiropod
# Encaminhar porta "NAT"
kubectl port-forward pod/meuprimeiropod 8080:80
# deletar um pod
kubectl delete pod meuprimeiropod
# Executando dois pod - Aula labes e selectors
kubectl apply -f meupodazul.yaml -f meupodverde.yaml
# seleciona pod pelo label
kubectl get pods -l versao=verde
kubectl get pods -l versao=azul
kubectl get pods -l app=nginx
kubectl delete pod -l versao=azul
# Iniciando Replicaset
kubectl apply -f meuprimeiroreplicaset.yml
# Listar Replicaset
kubectl get replicaset
# descrever Replicaset
kubectl describe replicaset meuprimeiroreplicaset
# escalar Replicaser
kubectl scale replicaset meuprimeiroreplicaset --replicas=3
# listar versão deployments
kubectl rollout history deployment meuprimeirodeployment
# Retornar a versão deployment
kubectl rollout undo deployment meuprimeirodeployment
# Retornar deployment de uma imagem especifica 
kubectl set image deployment meuprimeirodeployment meucontainer=kubedevio/nginx-color:green
# Listar services
kubectl get services
# Comando teste aula services
docker container run --rm kubedevio/ubuntu-curl curl http://10.116.0.2:32063/temperatura/fahrenheitparacelsius/100 
kubectl run -i --tty --image kubedevio/ubuntu-curl ping-teste --restart=Never --rm -- /bin/sh
curl http://10.116.0.2:32063/temperatura/fahrenheitparacelsius/100 
curl http://api-service/temperatura/fahrenheitparacelsius/100 
# Listar todos os componetens
kubectl get all
# Listar endpoint
kubectl get endpoints
# Listar ConfigMaps
kubectl get configmap
# Detalhes do Configmap
kubectl describe configmap
# Criar configMap via linha de comando
kubectl create configmap literal-configmap --from-literal=Mongo__Host=mongo-service
# Criar configMap via linha de comando usando um arquivo
kubectl create configmap file-configmap --from-file=prometheus.yaml






