## Config map can shows for us in which cloud we are operating

  1. To create configmap please run such command:
     > For azure context
      ```
      kubectl apply -f - <<EOF
      data:
        ENV_CLOUD: AZURE
      apiVersion: v1
      kind: ConfigMap
      metadata:
        name: cloudconfigmap
      EOF
       ``` 
     > For google context
     ```
     kubectl apply -f - <<EOF
     data:
       ENV_CLOUD: GOOGLE
     apiVersion: v1
     kind: ConfigMap
     metadata:
       name: cloudconfigmap
     EOF
      ``` 
