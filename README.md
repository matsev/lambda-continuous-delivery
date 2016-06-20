# Continuous Delivery for AWS Lambda

Sample project that shows how [AWS Lambda Aliases](https://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html) can be
used to enable continuous integration.

Please read the [blog post](https://www.jayway.com/2016/07/07/continuous-deployment-aws-lambda/) for details.


## Tools

In order to execute the scripts, you need to install the following tools:

- [AWS CLI](https://aws.amazon.com/cli/) (AWS Command Line Interface)
- [jq](https://stedolan.github.io/jq/) (JSON Command Line Processor)


## CloudFormation Template

[cloudformation.template](cloudformation.template)

## Scripts

### Create stack

- [0-create-stack.sh](scripts/0-create-stack.sh)

### Pipeline Steps

| Script                                                        | Description               |
| ------------------------------------------------------------- | ------------------------- |
| [1-test.sh](scripts/1-test.sh)                                | Execute unit tests        |
| [2-package.sh](scripts/2-package.sh)                          | Create .zip               |
| [3-update-lambda.sh](scripts/3-update-lambda.sh)              | Update Lambda             |
| [4-integration-test.sh](scripts/4-integration-test.sh)        | Execute integration tests |
| [5-publish-version.sh](scripts/5-publish-version.sh)          | Publish Lambda version    |
| [6-update-stage-alias.sh](scripts/6-update-stage-alias.sh)    | Update stage alias        |
| [7-update-prod-alias.sh](scripts/7-update-prod-alias.sh)      | Update prod alias         |

### Pipeline Script

- [build-and-deploy-to-stage.sh](scripts/build-and-deploy-to-stage.sh)

### Support Script

- [update-alias.sh](scripts/update-alias.sh)

