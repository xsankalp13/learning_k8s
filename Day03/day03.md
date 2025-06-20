## What I have learned today
- what is kind
- how to create a cluster using kind
- how to create a cluster using kind with a specific version of kubernetes
- basics of yaml
- creat a cofig file and use it to create a cluster

## task for the day
- [*] task 1 
    - Create a pod using the imperative command and use ngnix as the image
- [*] task 2
    - Create the YAML from the nginx pod created in task 1
    - Update the pod name in the YAML file
    - Use that YAML to create a new pod with name nginx-new
- [*] task 3
    - Apply the below YAML and fix the errors, including all the commands that you run during the troubleshooting and the error message

    ```yaml
    apiVersion: v1
    kind: Pod
    metadata:
    labels:
        app: test
    name: redis
    spec:
    containers:
    - image: rediss
        name: redis
    ```