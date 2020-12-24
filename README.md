# okta-reg-user-lambda

An example of AWS lambda designed to create users in Okta by API calls from SPA

1. Upload `functions.zip` to S3 bucket and record bucket name and key, you will need them while deploying the stack
2. Open AWS CloudFormation Console https://console.aws.amazon.com/cloudformation/home and select "Create stack (with new resources)" from "Template ready" and choose to "Upload a template file"
3. Select `lambda.yml` from this repository, then "Next"
4. Give stack a name (okta-registration)
5. Provide parameters for the stack
  - FrontEndDomain - URL where your web-application is hosted, it's required to provide CORS headers
  - LambdaBucket - S3 bucket name where you uploaded `function.zip`
  - LambdaKey - S3 key for `function.zip`
  - OktaOrgUrl - URL for your Okta organization (https://xxxxx.okta.com)
  - OktaApiToken - API token generated for your Okta org (it should have create user privileges)
6. Click "Next" and "Next" again to Review step
7. Check all 3 checkboxes at the bottom and click "Create Stack"
8. Wait till stack is created and you see status "Create Complete"
9. After that select tab "Outputs" and copy API URL, which you need to use in your front-end application
