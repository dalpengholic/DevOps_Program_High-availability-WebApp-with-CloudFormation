# Major Steps
## 1. Download
- Go to Terminal and make a folder and clone the repository in the folder.
`git clone https://github.com/dalpengholic/DevOps_Project2_WebApp_AWS_CloudFormation.git`
- Go to files folder.

## 1. BaseInfra.yml
- Execute BaseInfra by running create.sh as follows. \
`./create.sh {YourStackName} {yml template file} {parameter json file}` \
ex) `./create.sh BaseInfraPro2 BaseInfra.yml BaseInfra-params.json`

## 2. S3Infra.yml
S3 Buckets or DBs are considered persistent objects. So it could be normal to use just console. In this example, two S3 buckets are going to be created using CloudFormation.\
- Open `S3Infra.yml` file and edit the both bucket names what ever you want because S3 is global service so that the name of bucket has to be unique. \
ex) In my case, `devops-project2-2020-forwebapp-lwj` for Web app. `devops-project2-2020-forbastion-lwj` for bastion host

- Execute S3Infra by running create.sh as follows. \
`./create.sh {YourStackName} {yml template file} {parameter json file}` \
ex) `./create.sh S3IfraPro2 S3Infra.yml After-params.json`


## 3. Create two keys of key pairs and upload one of them.
- Go to EC2 service using AWS console. Go to `Key Pairs` under `NETWORK & SECURITY` located in left side bar.
- Create two key pair. One is needed to access bastion host(jump box) in public subnet. The other is needed to access to web servers from the bastion host. Afte creation, two keys are automatically saved in your local environment.
ex) The names of keys could be `ToBastion` and `ToWebServers`
- Go to S3 service using AWS console and upload `ToWebServers` to the S3 bucket you created already for bastion host. In my case. the bucket name is `devops-project2-2020-forbastion-lwj`.
- Upload 



