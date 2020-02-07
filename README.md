#  Deploy a high-availability web app using CloudFormation
## Udacity Cloud DevOps Project2

## Table of Contents
1. [Project Goal](#project_goal)
2. [Infrastructure Diagram](#infrastructure_diagram)
3. [How to Use](#how_to_use)    
  1. [Dependency](#dependecy)
  2. [Steps](#steps)
4. [File Structure](#file_structure)
5. [Reference](#reference)
6. [License](#license)
7. [Acknowledgements](#acknowledgements)


<a name="project_goal"></a>
## Project Goal
Make web servers with high-availability using CloudFormation

### Requirements
- Create a custom VPC for this project. Attach IGW(Internet Gateway) to the VPC. 
- Deploy four servers(EC2 instances) using `Launch Configuration`. Two of the servers need to be located in each of two private subnets.
- Server specs: two vCPUs and at least 4GB of RAM. The Operating System to be used is Ubuntu 18. Allocate at least 10GB of disk space.
- Create a S3 bucket for the severs. Attach `IAM Role` to servers to use the bucket.
- Create a load balancer(Application Load Balancer) in public subnets. Set Load Balancer Health Check, Security Group, Target Group

<a name="infrastructure_diagram"></a>
## Infrastructure Diagram
blah
blah

<a name="how_to_use"></a>
## How to use
<a name="dependency"></a>
### Dependency
- AWS Command Line Interface

Go to Terminal and activate virtual environment and execute `pip install awscli` 

- AWS IAM
1. Create new user. Type user name, check `programmatic access` and click `Next`
2. Create group. Click create group, type group name, check `AdministratorAccess` and click `create group`
3. Add user to group. Click the created group, click `Next`
4. Click `Next`
5. See review. Click `Create user` if it is ok
6. `Acesss key ID` and `Secret access key` are going to used in aws cli 

- AWS CLI configuration
1. Go to Terminal and activate the virtual environment
2. Type `aws configure`
3. Input `Acesss key ID`, `Secret access key` created above, region name (ex: us-west-2) and skip output format by click enter
4. Check my configuration is ok by typing `aws s3 ls` or `aws iam get-user`

<a name="steps"></a>
### Steps
[here](https://github.com/dalpengholic/DevOps_Project2_WebApp_AWS_CloudFormation/blob/master/pics/Quick_manual.md)

<a name="file_structure"></a>
## File Structure
```
├── README.md
├── files
│   ├── After-params.json
│   ├── BaseInfra-params.json
│   ├── BaseInfra.yml
│   ├── BastionInfra.yml
│   ├── S3Infra.yml
│   ├── Udagram.zip
│   ├── UdagramInfra.yml
│   ├── create.sh
│   └── update.sh
├── pics
    ├── Infra_Diagram.png
    └── Quick_manual.md

```

<a name="reference"></a>
## Reference
blah
blah

<a name="license"></a>
## License
blah
blah

<a name="acknowledgements"></a>
## Acknowledgements
blah
blah
