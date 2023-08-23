## Adding a service account

  A service account bearer token is required to view the Kubernetes resources on this cluster. This can be created using kubectl while connected to your cluster via CLI.
  ![](/pic/tocken-setup-1.jpg)



  1. With the kubeconfig file pointing to the apiserver of your Kubernetes cluster, run this command to create a service account. This example creates the service account in the default namespace, but you can substitute any other namespace for default.\
     ```kubectl create serviceaccount arc-user -n default```
  2. Create ClusterRoleBinding to grant this service account the appropriate permissions on the cluster. If you used a different namespace in the first command, substitute it here for default.
     ```kubectl create clusterrolebinding arc-user-binding --clusterrole cluster-admin --serviceaccount default:arc-user```
  3. Create a service account token:
     ```
      kubectl apply -f - <<EOF
      apiVersion: v1
      kind: Secret
      metadata:
        name: arc-user-secret
        annotations:
          kubernetes.io/service-account.name: arc-user
      type: kubernetes.io/service-account-token
      EOF
     ```

     ``` TOKEN=$(kubectl get secret arc-user-secret -o jsonpath='{$.data.token}' | base64 -d | sed 's/$/\n/g')```
    
     ![](/pic/tocken-setup-2.jpg)
  4. Switch context of kubernetes cluster and create service account token to second cluster:\
    - ``` kubectl config get-contexts ```
    -  ```kubectl config use-context aks-webinar-francecentral-001 ```


## Token addon result
  ![](/pic/tocken-setup-3.jpg)