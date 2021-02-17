# eks-fargate-tutorial
A tutorial on using EKS or ECS with fargate on the AWS Cloud


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

* When running you can then query the 



### References

* [Fargate-AWS](https://aws.amazon.com/getting-started/hands-on/build-modern-app-fargate-lambda-dynamodb-python/module-two/)
* [Python-Fargate-AWS](https://github.com/aws-samples/aws-modern-application-workshop/tree/python/module-2)

