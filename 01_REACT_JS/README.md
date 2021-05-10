# Amplify
- [Amplify Getting Started](https://docs.amplify.aws/start)

# Starting React App

```sh
source ~/.bash_profile
npx create-react-app kio-compare-your-property-rjs-app
```

# Amplify

## configure

- Just when is a new aws account
```sh
amplify configure
```


## init

```sh
amplify init
# Scanning for plugins...
# Plugin scan successful
# Note: It is recommended to run this command from the root of your app directory
# ? Enter a name for the project kiocompareyourproper
# ? Enter a name for the environment kcyprjaenv
# ? Choose your default editor: Visual Studio Code
# ? Choose the type of app that you're building javascript
# Please tell us about your project
# ? What javascript framework are you using react
# ? Source Directory Path:  src
# ? Distribution Directory Path: build
# ? Build Command:  npm run-script build
# ? Start Command: npm run-script start
# Using default provider  awscloudformation

# For more information on AWS Profiles, see:
# https://docs.aws.amazon.com/cli/latest/userguide/cli-multiple-profiles.html

# ? Do you want to use an AWS profile? Yes
# ? Please choose the profile you want to use kio-indoor-emap
# Adding backend environment kcyprjaenv to AWS Amplify Console app: d27calhvr9nc4h
# ⠇ Initializing project in the cloud...

# CREATE_IN_PROGRESS DeploymentBucket AWS::S3::Bucket Sun May 09 2021 20:28:39 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS UnauthRole       AWS::IAM::Role  Sun May 09 2021 20:28:39 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS AuthRole         AWS::IAM::Role  Sun May 09 2021 20:28:39 GMT-0500 (Colombia Standard Time) Resource creation Initiated
# CREATE_IN_PROGRESS DeploymentBucket AWS::S3::Bucket Sun May 09 2021 20:28:38 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS AuthRole         AWS::IAM::Role  Sun May 09 2021 20:28:38 GMT-0500 (Colombia Standard Time)                            
# CREATE_IN_PROGRESS UnauthRole       AWS::IAM::Role  Sun May 09 2021 20:28:38 GMT-0500 (Colombia Standard Time)                            
# ⠇ Initializing project in the cloud...

# CREATE_COMPLETE AuthRole   AWS::IAM::Role Sun May 09 2021 20:28:51 GMT-0500 (Colombia Standard Time) 
# CREATE_COMPLETE UnauthRole AWS::IAM::Role Sun May 09 2021 20:28:51 GMT-0500 (Colombia Standard Time) 
# ⠧ Initializing project in the cloud...

# CREATE_COMPLETE amplify-kiocompareyourproper-kcyprjaenv-202834 AWS::CloudFormation::Stack Sun May 09 2021 20:29:02 GMT-0500 (Colombia Standard Time) 
# CREATE_COMPLETE DeploymentBucket                               AWS::S3::Bucket            Sun May 09 2021 20:29:00 GMT-0500 (Colombia Standard Time) 
# ✔ Successfully created initial AWS cloud resources for deployments.
# ✔ Initialized provider successfully.
# Initialized your environment successfully.

# Your project has been successfully initialized and connected to the cloud!

# Some next steps:
# "amplify status" will show you what you've added already and if it's locally configured or deployed
# "amplify add <category>" will allow you to add features like user login or a backend API
# "amplify push" will build all your local backend resources and provision it in the cloud
# “amplify console” to open the Amplify Console and view your project status
# "amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud

# Pro tip:
# Try "amplify add api" to create a backend API and then "amplify publish" to deploy everything

```

# Codecommit

[Create repo](https://docs.aws.amazon.com/cli/latest/reference/codecommit/create-repository.html)
```sh
nano ~/.aws/credentials
export PATH=~/Library/Python/3.8/bin:$PATH
# source ~/.bash_profile
# test
aws s3 ls --profile kio-indoor-emap
export AWS_PROFILE=kio-indoor-emap

# aws codecommit create-repository --repository-name MyDemoRepo --repository-description "My demonstration repository" --tags Team=Saanvi
aws codecommit create-repository --repository-name kio-compare-your-property-rjs-app --repository-description "Compare yourself property" --tags Team=kio --region us-east-1 

```

## result
```json
{
    "repositoryMetadata": {
        "accountId": "429849394467",
        "repositoryId": "2a77539d-3ff9-49ad-bd24-ce162bdaaa47",
        "repositoryName": "kio-compare-your-property-rjs-app",
        "repositoryDescription": "Compare yourself property",
        "lastModifiedDate": "2021-05-09T20:33:56.359000-05:00",
        "creationDate": "2021-05-09T20:33:56.359000-05:00",
        "cloneUrlHttp": "https://git-codecommit.us-east-1.amazonaws.com/v1/repos/kio-compare-your-property-rjs-app",
        "cloneUrlSsh": "ssh://git-codecommit.us-east-1.amazonaws.com/v1/repos/kio-compare-your-property-rjs-app",
        "Arn": "arn:aws:codecommit:us-east-1:429849394467:kio-compare-your-property-rjs-app"
    }
}
```


# git

```sh
ssh-keygen
/Users/robin8a/.ssh/kio_smart_contracts_rsa

cat ~/.ssh/kio_smart_contracts_rsa.pub

```


```sh
cd ~/.ssh
ls
nano config

# Add

# CodeCommit hosts
# Host kio_smart_contracts_rsa
#    HostName git-codecommit.us-east-1.amazonaws.com
#    User AKIAWIFIFHURQXRLUPPD
#    IdentityFile ~/.ssh/kio_smart_contracts_rsa

```

https://xiaolishen.medium.com/use-multiple-ssh-keys-for-different-github-accounts-on-the-same-computer-7d7103ca8693

```sh
# git remote -v
# git remote rm origin
# Using the same kio_indoor_emap_rsa because is on the same account
git remote add origin ssh://kio_indoor_emap_rsa/v1/repos/kio-compare-your-property-rjs-app
git push
```



# Install libraries
```sh
npm install react-bootstrap bootstrap
npm i react-external-link
npm i react-router-dom
npm i aws-amplify @aws-amplify/ui-react
npm i aws-amplify-react
npm i --save react-select
npm i styled-components
npm i uuid
```


# Amplify hosting
```sh
amplify add hosting
```
## Result
```sh
amplify add hosting
? Select the plugin module to execute Hosting with Amplify Console (Managed hosting with custom domains, Continuous deployment)
? Choose a type Continuous deployment (Git-based deployments)
? Continuous deployment is configured in the Amplify Console. Please hit enter once you connect your repository 
Amplify hosting urls: 
┌──────────────┬────────────────────────────────────────────┐
│ FrontEnd Env │ Domain                                     │
├──────────────┼────────────────────────────────────────────┤
│ main         │ https://main.d1l1kwcqq235gy.amplifyapp.com │
```

# Amplify auth

```sh
amplify add auth
# Using service: Cognito, provided by: awscloudformation
 
#  The current configured provider is Amazon Cognito. 
 
#  Do you want to use the default authentication and security configuration? Default configuration
#  Warning: you will not be able to edit these selections. 
#  How do you want users to be able to sign in? Username
#  Do you want to configure advanced settings? No, I am done.
# Successfully added resource kiosmartcontractrjsa43ea2996 locally

# Some next steps:
# "amplify push" will build all your local backend resources and provision it in the cloud
# "amplify publish" will build all your local backend and frontend resources (if you have hosting category added) and provision it in the cloud
```

# Amplify push

```sh
amplify push
```

# Credentails


# Amplify pub and sub example with React

- [aws-amplify-react-iot-pub-sub-demo](https://github.com/matwerber1/aws-amplify-react-iot-pub-sub-demo)
- [Get cognito Identity Id](https://docs.aws.amazon.com/cognitoidentity/latest/APIReference/API_GetId.html)

```sh
export AWS_PROFILE=kio-indoor-emap
aws iot attach-principal-policy --policy-name 'ReactIoTPolicy' --principal '<YOUR_COGNITO_IDENTITY_ID>'
# aws iot attach-principal-policy --policy-name 'ReactIoTPolicy' --principal 'us-west-2:d8b273d6-8d18-4fe7-81df-7d2ddd77587a'
aws iot attach-principal-policy --policy-name 'ReactIoTPolicy' --principal 'us-east-1_YqbWZ4GAp'

```

