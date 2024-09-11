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



