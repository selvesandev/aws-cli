# aws-cli

## Profile

* `aws confirgure`

```
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: json
```

* `aws configure --profile profile_name`

```
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: text
```

* `export AWS_DEFAULT_PROFILE=profile_name` To switch to a different profile than default.


## LAMBDA

### List Lambda Functions

`aws lambda list-functions`

### Execute a lambda from CLI

* `aws lambda invoke --function-name augmenter-dev response.json [--profile moichor]`
* https://docs.aws.amazon.com/cli/latest/reference/lambda/invoke.html

```
aws lambda invoke \
    --function-name my-function \
    --payload '{ "name": "Bob" }' \
    response.json
```
* Delete a function `aws lambda delete-function --function-name function_name`


#### Deploy a zipped SAM build

* `cd root_dir`
* `sam build`
* `sam local invoke` (open docker)
* `zip everything that is inside .aws-sam/build/yourFunction/*`
* `aws lambda update-function-code --function-name "myFunction" --zip-file "fileb://./app.zip" --region "us-east-2"`


## Serverless

* `aws create --template` to list all the available template.
* `sls invoke -f hello` invoke a lambda function




