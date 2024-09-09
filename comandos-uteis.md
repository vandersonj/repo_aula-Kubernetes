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



