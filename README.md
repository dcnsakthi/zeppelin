# zeppelin
Apache Zeppelin - Kubernetes


## Steps
- Create Namespace on Kubernetes `kubectl create namespace zeppelin`
  >>Expected Output \
  `namespace/zeppelin created`
- Create Deployment with [zeppelin-server.yaml](https://raw.githubusercontent.com/dcnsakthi/zeppelin/main/zeppelin-server.yaml) in `zeppelin` namespace `kubectl apply -f zeppelin-server.yaml -n zeppelin`
    >>Expected Output \
    `configmap/zeppelin-server-conf-map created` \
    `configmap/zeppelin-server-conf created` \
     `deployment.apps/zeppelin-server created` \
     `service/zeppelin-server created` \
     `serviceaccount/zeppelin-server created` \
     `role.rbac.authorization.k8s.io/zeppelin-server-role created` \
     `rolebinding.rbac.authorization.k8s.io/zeppelin-server-role-binding created` \
- Verifiy the Deployment `kubectl get pods,svc -n zeppelin`
     >>Expected Output \
     `NAME                                   READY   STATUS    RESTARTS   AGE` \
     `pod/zeppelin-server-7f659d4cbc-d4zq4   3/3     Running   0          1m` \
     `NAME                      TYPE           CLUSTER-IP   EXTERNAL-IP      PORT(S)                        AGE` \
     `service/zeppelin-server   LoadBalancer   #.#.#.#      #.#.#.#          80:30396/TCP,12320:31696/TCP   31h `
- Access your zeppelin using `service/zeppelin-server` External-IP on port 80 
    >>Expected Output \ 
    `Replace #.#.#.# with real IP (http://#.#.#.#)`
- Happy Learning! :) 
