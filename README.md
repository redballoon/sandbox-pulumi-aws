# Sandbox-Pulumi-Aws
Sandbox to play around with Infra as Code (IaC) and document permissions/resources required to generate something similar to Serverless framework but using Pulumi framework.

## WHY ?
Pulumi promises more granular control but with that your responsibility increases by a lot.
You are now required to know all the individual resources required to standup and connect
several resources. Essentially all the nitty gritty stuff that happens behind the scenes
in an out of the box solution like Serverless Framework.

So why?
- There are many architecture scenarios that are not achievable by Serverless alone,
you will eventually need to learn an additional item like cloudformation or terraform.
- Whichever IaC you choose, you will be locked into whatever Language that item uses.
- Since Pulumi can leverage javascript, you don't end up wasting time
learning a specific language.
- It would force the developer to learn AWS Cloud more in depth.
- A lot of what you learn will be regarding what configurations are available per
service and what CAN be done which will be valuable information when Architecting an app from scratch.
- It essentially lowers the learning curve since you have 1 less thing to learn (language specific templating)
- Serverless does a good job of doing a lot of the required work behind the scenes, if we can just inspect
the work that is being done we can lower the learning curve even more because given a question like:
"Given best practices, what resources I need to standup a lambda function and attach it to a HTTP API"
We can simply see how Serverless does it, document it, and we now have a playbook on what we need
to do in Pulumi and narrow our google searches to just what we need.
- This will also allow the dev to learn how complicated it is to leverage a combination of
both Pulumi and Serverless if needed.



###  Recipe: Lambda + HTTP API Gateway

will launch a basic API Gateway (HTTP) + Lambda Function

TODO:
we should be able to run the same example with Serverless and Pulumi with
similar results

```
cd ./Lambda

# shortcuts for Serverless
npm run sls:deploy:lambda


# shortcut for Pulumi
// npm run sls:deploy:lambda:pm
```



### Commands

** Deployment **
```
# https://www.serverless.com/framework/docs/providers/aws/guide/quick-start
# https://www.serverless.com/framework/docs/providers/aws/cli-reference/deploy

# shortcut
cd ./Lambda && npm run sls:deploy:lambda

# assume stage=dev is by default, region NEEDS to be set explicitly :/
serverless deploy --verbose --region us-west-2 --config ./Lambda/serverless.yml

serverless deploy --verbose --config ./Lambda/serverless.yml --stage dev --region us-west-2
```
