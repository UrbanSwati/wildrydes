If a you run into any trouble I have located the scripts necessary to **easily** create the full application in the **North Virginia** region.

This is not a fully automated process:

- Step 1 creates a **S3** **bucket** that needs to be inputted as a parameter into steps **2** and **4**.
- Step 2 creates a **Cognito** user pool that needs to be inputted as a parameter into step **4**.

 

1. Static Web Hosting

   https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=wildrydes-webapp-1&templateURL=https://s3.amazonaws.com/wildrydes-us-east-1/WebApplication/1_StaticWebHosting/webapp-static-hosting.yaml    

   Get the Name of the S3 bucket in the output of the CloudFormation template

2. User Management

   https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=wildrydes-webapp-2&templateURL=https://s3.amazonaws.com/wildrydes-us-east-1/WebApplication/2_UserManagement/user-management.yaml  

   - Input the s3 bucket Name
   - Copy the ARN of the Cognito user pool located starting at <https://console.aws.amazon.com/cognito/users/?region=us-east-1>

3. Serverless Backend

   No script is necessary as the Script is included in step 4

4. RESTful APIs

   https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=wildrydes-webapp-4&templateURL=https://s3.amazonaws.com/wildrydes-us-east-1/WebApplication/4_RESTfulAPIs/backend-api.yaml    

   - Input the s3 bucket Name
   - Input the ARN of the Cognito user pool
