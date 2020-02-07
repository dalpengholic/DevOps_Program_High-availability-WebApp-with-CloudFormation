# Major Steps
## 1. Download
- Go to Terminal and make a folder and clone the repository in the folder.
`git clone https://github.com/dalpengholic/DevOps_Project2_WebApp_AWS_CloudFormation.git`
- Go to `files` folder that in the folder you have made.

## 2. BaseInfra.yml
- Execute `BaseInfra.yml` by running create.sh as follows. \
`./create.sh {YourStackName} {yml template file} {parameter json file}` \
ex) `./create.sh BaseStackPro2 BaseInfra.yml BaseInfra-params.json`

## 3. S3Infra.yml
S3 Buckets or DBs are considered persistent objects. So it could be normal to use just console. In this example, two S3 buckets are going to be created using CloudFormation.\
- Open `S3Infra.yml` file and edit the both bucket names what ever you want because S3 is global service so that the name of bucket has to be unique. \
ex) In my case, `devops-project2-2020-forwebapp-lwj` for Web app. `devops-project2-2020-forbastion-lwj` for bastion host

- Execute `S3Infra.yml` by running create.sh as follows. \
`./create.sh {YourStackName} {yml template file} {parameter json file}` \
ex) `./create.sh S3StackPro2 S3Infra.yml After-params.json`

## 4. Create two keys of key pairs and upload one of them.
- Go to EC2 service using AWS console. Go to `Key Pairs` under `NETWORK & SECURITY` located in left side bar.
- Create two key pair. One is needed to access bastion host(jump box) in public subnet. The other is needed to access to web servers from the bastion host. Afte creation, two keys are automatically saved in your local environment.
ex) The names of keys could be `ToBastion` and `ToWebServers`. In my cases, they are `Udacity_Pro2_ToBastion` and `Udacity_Pro2_ToWebServers`.

- Go to S3 service using AWS console and upload `ToWebServers` key to the S3 bucket you have created already for bastion host. In my case. the bucket name is `devops-project2-2020-forbastion-lwj`. Never upload `Udacity_Pro2_ToBastion` for the safety of your network. It has to be only in your local environment.

- Upload `Udagram.zip` which is located in `files` folder to the S3 bucket you have created already for web servers. In my case. the bucket name is `devops-project2-2020-forwebapp-lwj`.

## 5. BastionInfra.yml
- Open `BastionInfra.yml` file and edit `MyIp` parameter(line 9). Change the value of `Default` to your IP address to restrict access. For example, my IP is 86.50.146.207 at the time I am writing. So it could be 86.50.146.207/32. To find current ip, go to `Google` and type `my ip`.

- Also edit `KeyForBastion` parameter(line 19). Change the value of `Default` to your name of key for bastion host to access web servers. The default value has to be the same as the file uploaded in the S3 bucket for the bastion hosts. In my case, the default value is `Udacity_Pro2_ToWebServers`. 

- Execute `BastionInfra.yml` by running create.sh as follows. \
`./create.sh {YourStackName} {yml template file} {parameter json file}` \
ex) `./create.sh BastionStackPro2 BastionInfra.yml After-params.json`

- Go to CloudFormation using AWS console. Click the stack name you just created. It is usuful to check the progress by clicking `Events`

- After creation of the stack, you must be able to access one of bastion hosts. In my case, I can access one of bastion hosts using the key, `Udacity_Pro2_ToBastion`. Go to EC2 and click `Instances`. Click one of bastion hosts and click `Connect`. Read the instruction and execute them.

## 6. UdagramInfra.yml
- Execute `UdagramInfra.yml` by running create.sh as follows. \
`./create.sh {YourStackName} {yml template file} {parameter json file}` \
ex) `./create.sh WebAppStackPro2 UdagramInfra.yml After-params.json`

- After creation of the stack, It could be possible to access a wep page ran by web servers. The address of web page can be found in the output section.

- To access one of webservers, go to  Go to EC2 and click `Instances`. Click one of web servers and click `Connect`. Read the instruction and execute them.







