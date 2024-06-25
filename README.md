# eks-cluster
eks cluster and its yaml files
steps:
# install kubectl on Amazon linux : https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/
# install eksctl on Amazon linux : https://docs.aws.amazon.com/emr/latest/EMR-on-EKS-DevelopmentGuide/setting-up-eksctl.html
aws configure
eksctl create cluster --name cluster-1  --version 1.30 --region us-east-1 --nodegroup-name demo-workers --node-type t2.micro --nodes 3  --nodes-min 1 --nodes-max 4 --managed
aws eks update-kubeconfig --name cluster-1 --region us-east-1
deploy the java,python and nodejs applications using  images uri's in ECR
and expose the applications by creating the loadbalancer services


final: delete the cluster using command ---> eksctl delete cluster --region=us-east-1 --name=cluster-1
