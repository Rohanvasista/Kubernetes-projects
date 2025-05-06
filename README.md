# Deploy a Simple Nginx Web App

Steps:
1. Create a Pod(pod.yaml)
   Apply it:kubectl apply -f nginx-pod.yaml,
            kubectl get pods ,
            kubectl describe pod nginx-pod
   
2. Create a ReplicaSet(replicaset.yaml)
   Apply it:kubectl apply -f nginx-replicaset.yaml, 
            kubectl get replicasets,
            kubectl get pods -l app=nginx

3. Create a Deployment(deployment.yaml)
   Apply it:kubectl apply -f nginx-deployment.yaml,
            kubectl get deployments,
            kubectl get pods -l app=nginx-deploy,
            kubectl rollout status deployment nginx-deployment
   
optional:
kubectl scale deployment nginx-deployment --replicas=5 (to scale up) ,
kubectl rollout undo deployment nginx-deployment (roll back)


4. Create a service(service.yaml) #To expose our application to outside world
  Apply it:kubectl apply -f deployment.yaml,
           kubectl apply -f service.yaml
Access via the port - http://localhost:30080/
o/p:
Welcome to nginx!
If you see this page, the nginx web server is successfully installed and working. Further configuration is required.

For online documentation and support please refer to nginx.org.
Commercial support is available at nginx.com.

Thank you for using nginx.

5. Clean up
   kubectl delete -f deployment.yaml,
   kubectl delete -f service.yaml,
   kubectl delete -f replicaset.yaml
   kubectl delete -f pod.yaml
   

   
