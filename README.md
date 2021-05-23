# ecs and eks fargate-tutorial or AWS App Runner
A tutorial on using EKS, ECS with fargate, or AWS App Ruuner on the AWS Cloud

### Verified Deploy with AWS App Runner

### ECS method

* setup app:  virtualenv + `make all`
* test app local:  `python app.py`
* curl it to test:  `curl localhost:8080/change/1/34`
* create ECR Repo
* build container
* push container
* run docker local:   `docker run -p 8080:8080 changemachine`
* deploy to fargate
* test public service


### EKS method


## Build a Fargate App

*  Install `kubectl` and `eksctl`.  You can [follow instructions here](https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html).
*  Open up either AWS CloudShell or AWS Cloud9
*  Create a cluster at the terminal `eksctl create cluster --name FargateExploration --region us-east-2 --fargate` (Takes a few minutes) 

You will see output similar to this

```bash
2021-02-17 17:52:07 [ℹ]  waiting for CloudFormation stack "eksctl-FargateExploration-cluster"
2021-02-17 17:52:28 [ℹ]  creating Fargate profile "fp-default" on EKS cluster "FargateExploration"
```


*   Verify the cluster:  `aws eks describe-cluster --name FargateExploration --query cluster.resourcesVpcConfig.clusterSecurityGroupId` (or leave off the query and get entire description)

* Create ECR Repo:

![change-machine](https://user-images.githubusercontent.com/58792/108248106-76726500-7121-11eb-8b30-3b6dd38c3853.png)

* ECS is much easier to setup with Fargate:  https://us-east-2.console.aws.amazon.com/ecs/home?region=us-east-2#/firstRun


### AWS App Runner method

This repository can easily be converted to an AWS Runner Method in Wizard to the following:

1.  For build do:  `pip install -r requirements.txt`
2.  To run:  `python app.py`
3.  For port:  `8080`


![1-aws-app-runner](https://user-images.githubusercontent.com/58792/119260856-bfafd600-bba2-11eb-941e-30c42dff6a16.png)
![app-service-logs](https://user-images.githubusercontent.com/58792/119261353-fedf2680-bba4-11eb-935e-9c2a837e7cb4.png)
![deployed-app-service](https://user-images.githubusercontent.com/58792/119261367-0f8f9c80-bba5-11eb-8889-365f4b3ca4c4.png)





### References

* [Fargate-AWS](https://aws.amazon.com/getting-started/hands-on/build-modern-app-fargate-lambda-dynamodb-python/module-two/)
* [Python-Fargate-AWS](https://github.com/aws-samples/aws-modern-application-workshop/tree/python/module-2)

