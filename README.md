This project creates EKS cluster via terraform and runs nginx in kubernetes namespace via ansible playbook and nginx-config.yaml file

cd terraform
terraform init
terraform apply
terraform apply --auto-approve


to find latest version of terraform modules:
git ls-remote https://github.com/terraform-aws-modules/terraform-aws-vpc.git
git ls-remote https://github.com/terraform-aws-modules/terraform-aws-eks.git


create kubeconfig file for eks cluster:
aws eks update-kubeconfig --region ap-southeast-2 --name x-eks-cluster --kubeconfig kubeconfig_ans_x_eks_cluster




cd ansible
ansible-playbook deploy_to_k8s.yaml



kubectl get ns
export KUBECONFIG=/Users/edgar/projects/devops_gitlab/15_ansible/15_ansible_deploy_k8s_tf/ansible/kubeconfig_ans_x_eks_cluste
ansible-playbook deploy_to_k8s.yaml
kubectl get ns


kubectl get pods -n k8s-namespace
kubectl get pods -A
kubectl get services -A











cd terraform

terraform destroy


[//]: # ()
[//]: # ()
[//]: # ()
[//]: # ([//]: # &#40;to check ansible inventory from dynamic inventory script, run the following command&#41;)
[//]: # (ansible-inventory -i inventory_aws_ec2.yaml --list)

[//]: # ()
[//]: # (ansible-inventory -i inventory_aws_ec2.yaml --graph)

[//]: # ()
[//]: # ()
[//]: # ()
[//]: # ([//]: # &#40;this allows to run ansible playbook with dynamic inventory script, which will get the list of EC2 instances from AWS and run the playbook on them&#41;)
[//]: # (ansible-playbook -i inventory_aws_ec2.yaml deploy_dockerapp.yaml)

[//]: # ()
[//]: # ()
[//]: # ()

