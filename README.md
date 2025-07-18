# Exploring AWS Identity and Access Management ( IAM )

## Project Goals
the project goal is to know What is IAM 

![Project Image](https://github.com/fadykaram88/Senior-1-/blob/main/1594668243636.png?raw=true)

## AWS Console Steps  

### Step 0  
```bash
Search about IAM  
```
### Step 1  
```bash
Create user 1 and user 2 and user 3 
```
### Note : don't forget to write the passward in the clipboard as you will need it later 
### other note : give them access to the AWS management console 

### Step 2  
```bash
 go to user groups and create 3 groups which are
EC2-admin
EC2-support
S3-support
```

### Step 3  
```bash
Choose EC2-support and give him policy (AmazonEC2ReadOnlyAccess)
```
### Note : AmazonEC2ReadOnlyAccess : it allows him to see a lot of AWS resources like EC2 and S3 and CloudWatch and EC2 Auto scaling  but not to create or modify any resource

### Step 4  
```bash
after adding the policy choose it then choose JSON so you will see
Effect : says whether to allow or deny the permission
Action : specify the API calls that can be made agianst an AWS service
Resource : It defines the scope of the policy to the user 
```
### Step 5 
```bash
Choose S3-support then attach policy and choose AmazonS3ReadOnlyAccess
```
### Note : AmazonS3ReadOnlyAccess : this policy gives the user the permission to see and list S3 buckets without ability to modify or delete or create new one 

### Step 6 
```bash
choose EC2-Admin then choose the permission which is EC2-Admin-Policy
but I have a question to you so what does this policy mean ?
```
### Step 7 
```bash
 
```


## Final Steps
1. Deploy Prometheus and Grafana in the cluster.
2. Link Prometheus with the app.
3. Link Grafana with Prometheus.
4. Add permissions for Prometheus to monitor the app.

## Notes
- The API server, scheduler, controller manager, etcd, kube-proxy, and kubelet are all created automatically after installing K3s.
- Ensure all services are running correctly and monitor them using Prometheus and Grafana.
