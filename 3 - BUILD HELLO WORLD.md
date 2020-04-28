#### project name
export PROJECT_NAME="sam-example"
#### AWS Quick Start Templates
export CHOISE_TEMPLATE=1 
#### nodejs runtime
export CHOISE_RUNTIME=1 

printf '%s\n' $CHOISE_TEMPLATE $CHOISE_RUNTIME $PROJECT_NAME | sam init

#### sam init 3 choises: 
####
#### Which template source would you like to use?
#### 	1 - AWS Quick Start Templates
#### 	2 - Custom Template Location
#### 
#### Which runtime would you like to use?
#### 	1 - nodejs12.x
#### 	2 - python3.8
#### 	3 - ruby2.7
#### 	4 - go1.x
#### 	5 - java11
####	6 - dotnetcore3.1
####	7 - nodejs10.x
####	8 - python3.7
####	9 - python3.6
####	10 - python2.7
####	11 - ruby2.5
####	12 - java8
####	13 - dotnetcore2.1
####	14 - dotnetcore2.0
####	15 - dotnetcore1.0
####
#### Project name [sam-app]: $PROJECT_NAME

#### enter the directory
cd $PROJECT_NAME

#### build artifacts
sam build

#### sam --help
#### sam local invoke - run local
#### sam local invoke "HelloWorldFunction" -e events/event.json

#### run node on localhost:3000/hello
sam local start-api 

#### https://console.aws.amazon.com/iam/home?####/security_credentials create access_key and secret_key, download csv
#### AWS DEPLOY
export AWS_ACCESS_KEY_ID="enter_the_access_key"

export AWS_SECRET_ACCESS_KEY="enter_the_secrete_key"

#### AWS REGION us-east-1, us-east-2, us-west-1... is region to deploy lambda function
export AWS_DEFAULT_REGION=us-east-2 

export CAPABILITY="CAPABILITY_IAM"

#### S3 DEPLOY

#### S3 REGION us-east-1, us-east-2, us-west-1...
export S3_REGION=us-east-2
#### S3 BUCKET NAME
export S3_BUCKET_NAME=mybucketbr123 

#### https://console.aws.amazon.com/s3/bucket/create?region=$S3_REGION to create s3 bucket

#### DEPLOY

sam deploy --stack-name $PROJECT_NAME --capabilities $CAPABILITY --region $AWS_DEFAULT_REGION --s3-bucket $S3_BUCKET_NAME

#### https://us-east-2.console.aws.amazon.com/lambda/home?region=$AWS_DEFAULT_REGION#/functions
#### @see https://us-east-2.console.aws.amazon.com/lambda/home?region=$AWS_DEFAULT_REGION#/applications/$PROJECT_NAME


Reference:

https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-getting-started-hello-world.html

https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html

https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html

https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-template-publishing-applications.html

https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-config.html

https://github.com/toml-lang/toml
