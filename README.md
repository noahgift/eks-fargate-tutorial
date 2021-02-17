# eks-fargate-tutorial
A tutorial on using EKS with fargate on the AWS Cloud


## Build a Fargate App

1.  Install `kubectl` and `eksctl`.  You can [follow instructions here](https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html).
2.  Open up either AWS CloudShell or AWS Cloud9
3.  Create a cluster at the terminal `eksctl create cluster --name FargateExploration --region us-east-2 --fargate` (Takes a few minutes) 
4.  Verify the cluster:  `aws eks describe-cluster --name FargateExploration --query cluster.resourcesVpcConfig.clusterSecurityGroupId`

