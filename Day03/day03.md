## What I have learned today
- what is kind
- how to create a cluster using kind
- how to create a cluster using kind with a specific version of kubernetes
- basics of yaml
- creat a cofig file and use it to create a cluster

## task for the day
- [*] task 1 
    - Create a pod using the imperative command and use ngnix as the image
        <details>

        <summary>
            Answer
        </summary>

        `kubectl run {pod_name} --image={image_name}` <br>
        
        example:<br>

            `kubectl run nginx-pod --image=nginx:latest`<br>
        </details>
- [*] task 2
    - Create the YAML from the nginx pod created in task 1
    - Update the pod name in the YAML file
    - Use that YAML to create a new pod with name nginx-new


        <details>

        <summary>
            Answer
        </summary>

        **Task 1**
            `kubectl run {pod_name} --image={image_name} --dry-run=client`<br>
            so that kubectl will create a pod but in dry run<br>
            
            now, 
            ```kubectl run {pod_name} --image={image_name} --dry-run=client -o yaml```


            so this will give you the yaml config file


            now to save the config file use,


            ```kubectl run {pod_name} --image={image_name} --dry-run=client -o yaml > {file_name}.yaml```
            
            example:

                `kubectl run nginx-pod --image=nginx:latest --dry-run=client -o yaml > pod.yaml`
        
        **Task 2**
            `vi {file_name}.yaml`
            and change the name parameter
        
        **Task 3**
            `kubectl create -f {file_name}.yaml`
            This will simply create a pod using provided yaml file

            example:
                `kubectl create -f pod.yaml`
        </details>


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

    <details>

    <summary>
        Answer
    </summary>

    Copy the above code and create a file name redis.yaml

    run
    `kubectl create -f redis.yaml`

    `kubectl get pods`
    you will notice that the pod in not ready

    to fix the error run,
    `kubectl edit pod {pod_name}`
    here our pod name is redis

    no locate image in the pod edit file
    change it to redis from rediss

    apply changes

    </details>