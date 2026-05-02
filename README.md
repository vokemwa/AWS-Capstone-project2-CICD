# Capstone Project 2: End-to-End CI/CD on AWS

## Prepare the application code
* created all the files as instructed using vs code as shown in the below screenshot.

![alt text](image.png)

## Create Elastic container registry (ECR)

* Search for ECR in the search bar
* Click the orange Create repository button
* Give it a name `myapp-repo`
* Create
* Below is the screenshot for the ECR

![alt text](image-1.png)

## Create Elastic container service (ECS)
  ### Create an ECS cluster
  * Go to ECS Clusters
  * Click create cluster
  * give it a cluster name `project-capstone2-cluster`
  * Under infrastructure, select `Fargate only`
  * Click create

  * Below is a screenshot of the cluster created

  ![alt text](image-2.png)

  ## AWS ECS Task definition
     ### Create a task definition for the ECS cluster
      * This is a blueprint for the application that tells Amazon ECS how to run the Docker containers
      * Click `Create new task definition`
      * Give it `task definition family name` `myapplication-task`
      * Launch type `AWS Fargate`
      * Select `Task execution role`

        * Below is the screenshot of the execution role

          ![alt text](image-3.png)

      * Under Container - 1
        * give it a name that matches the appspec.yaml file
        * Paste ECR Image url: `541426239397.dkr.ecr.us-east-1.amazonaws.com/myapp-repo`
        * Port mappings: Container port: `3000` Protocol: `TCP`, Port name: `myapplication-3000-tcp`
        * Click Create

        * Below is the screenshot for the task definition 
        
    ![alt text](image-7.png)


