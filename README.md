Create keypair.
ssh-keygen -t rsa -f ec2key 
Create EC2 instance
Terraform init
Terraform apply
initiate kind.yaml and kind.sh files
scp -i ec2key init_kind.sh kind.yaml ip:/tmp
login to Nwely created ec2
ssh -i ec2key ip
move to tmp directory 
cd /tmp
Create key pair to connect to git and Update git with the key pair
ssh-keygen -t rsa -f ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub
execute the kind envairoment
chmod 777 init_kind.sh
./init_kind.sh
install git
sudo yum install git
clone the git account 
git clone git@github.com:Surojit2023/ProjectA2.git
cd ProjectA2
Create Namespace project-2a
kubectl create namespace project-2a 
Deploy mysql manifest yaml files to create pods
kubectl apply -f mysql-pod.yaml -n project-2a
kubectl apply -f mysql-deployment.yaml -n project-2a
kubectl apply -f mysql-service.yaml -n project-2a
List all pods in project-2a
kubectl get all -n project-2a
Deploy app manifest yaml files to create pods
kubectl apply -f frontend-pod.yaml -n project-2a
kubectl apply -f frontend-service.yaml -n project-2a
kubectl apply -f frontend-deployment.yaml -n project-2a
List all pods in project-2a
kubectl get all -n project-2a
Test that you can access the app from inside EC2 and from the web browzer 
http://52.87.190.170:30000
curl localhost:30000
Deploy replica manifest yaml files to create pod replicas 
kubectl apply -f mysql-replica.yaml -n project-2a
kubectl apply -f frontend-replica.yaml -n project-2a

