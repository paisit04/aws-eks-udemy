# Amazon EKS Starter: Docker on AWS EKS with Kubernetes

https://www.udemy.com/course/amazon-eks-starter-kubernetes-on-aws/

https://courses.datacumulus.com/downloads/amazon-eks-starter-8ur to download the code.

## Prerequisites Test

```bash
aws --version
eksctl version
kubectl version --short --client
```

## EKS Setup
```bash
eksctl create cluster -f ./eks-course.yaml
kubectl get nodes
```

## cluster
```bash
eksctl get cluster
eksctl get nodegroup --cluster EKS-course-cluster
eksctl scale nodegroup --cluster EKS-course-cluster --nodes=5 --nodes-max=5 --name=ng-1
eksctl scale nodegroup --cluster EKS-course-cluster --nodes=3 --name=ng-1
```

## nodegroup
```bash
# add a nodegroup
eksctl create nodegroup --config-file=eks-course.yaml --include='ng-mixed'
eksctl get nodegroup --cluster EKS-course-cluster

# delete a nodegroup
eksctl delete nodegroup --config-file=eks-course.yaml --include=ng-mixed --approve
eksctl get nodegroup --cluster EKS-course-cluster
```
