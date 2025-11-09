To enable port 80 run the below command
sudo KUBECONFIG=$HOME/.kube/config kubectl port-forward -n ingress-nginx svc/ingress-nginx-controller 80:80  

Simple notes:
Pod:
Even though the container port defined in yaml is 9090, application is lisneting on port 8080:
>kubectl apply -f pod.yaml

>kubectl exec pod/web-image -it -- sh -c "netstat -tuln || ss -tuln"
- this command told my port was running on 8080

- updated the port in the yaml file from 9090 to 8080.
- But keeping run the container in pod.yaml is not the proper way to doing things.
