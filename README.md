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
1. ETL Pipeline : Original log file of Sparkify given by Udacity is loaded in a dataframe of Apache Spark dataframe and preprocessed(extraction, transformation, and loading) to make a dataframe for a machine learning pipeline.
2. ML pipeline : Prediction model is built and trained with the dataframe from ETL pipeline to predict potential churn users.
3. Flask Web App : A web app contains the visual summary of a dataset used training a model and a prediction page that an user of this web can input a basic data of a Sparkify user and get a prediction result.

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

<a name="file_structure"></a>
## File Structure
blah
blah

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
