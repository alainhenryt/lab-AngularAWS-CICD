# Building a CI/CD on AWS for an Angular Application using the AWS CodePipeline Service.

## STEPS:

Clone or download as zip this repo.
Create a github repo with any name of your choice.
Edite <lab-AngularAWS-CICD> to your github repo-name in all files that it is present
using crt+F(find and replace).
Now, push that to your github Repo.

## Sign in to SonarCloud at https://sonarcloud.io/ through github
1. Click on plus sign, ANALYZE NEW PROJECT
2. Import your src repo from github
3. Select repo, CREAT PROJECT MANUALLY

YOU SHOULD HAVE SOMETHING LIKE THIS BELOW:
-----------------------------------------------------------------
# SONAR SCANNER SET-UP INFO

#Configure the SONAR_TOKEN environment variable
Name of the environment variable: SONAR_TOKEN 
Value of the environment variable: <YOUR_GENERATED_TOKEN_IS_HERE> 

Execute the SonarScanner from your computer
Run the following command in your project's folder.

sonar-scanner \
  -Dsonar.organization=<YOUR_ORG_NAME> \
  -Dsonar.projectKey=lab-AngularAWS-CICD \
  -Dsonar.sources=. \
  -Dsonar.host.url=https://sonarcloud.io

--------------------------------------------------------------

EDITE the buildspec.yml file with above generated information
and push the changes to your github Repo.
## buildspec.yml

https://github.com/alainhenryt
/lab-AngularAWS-CICD/blob/master/buildspec.yml


## S3 bucket policy
1. Create an s3 bucket, allow public access, and attched below policy at link:
https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteAccessPermissionsReqd.html

1. Edite the <Bucket-Name> to yours and save.
2. Click on your Bucket-Name, select properties, scroll down the page and enable "Static website hosting"

## Open Codepipline service to creat your pipeline
1. Create a connection to your github repo & select your repo this codes.
2. At the level of creating a project, select ubuntu.
3. At Deploy level of setup, select your s3 bucket created ealier, enable "Extract file before deploy"