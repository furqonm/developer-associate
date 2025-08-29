Setting up the demo environment

Task 1: Setting up the demo code
1. Download the file with the same folder structure, which contains the source code and template, and place it to your local disk **demo_code**
2. Create an S3 bucket (or use an existing S3 bucket) and upload the demo_code folder with the existing structure. For reference, let's refer to this bucket as your demo-code bucket.

Task 2: Creating the sandbox demo environment
1. Dowload the sanbox_template.yml file below. You will use this template to create the sandbox environment **sandbox_template_v4.yml**
This demo sandbox creates an S3 public website. If you do not have the s3:GetObject permission, you will not be able to add a S3 bucket policy, so contact your administrator to add the permission to your account. 
Meanwhile, in your AWS CloudFormation template, comment the code (line numbers 321–331) related to the webBucketPolicy resource, and proceed with the next steps. After the stack is completed and you have been granted the appropriate permissions, modify the pollyNotesWeb bucket to add s3:GetObject bucket policy permission. 
The appendix includes a sample bucket policy. If you are using this sample bucket policy, remember to change the bucket name.

2. Create an AWS CloudFormation stack by using the sandbox_template.yml template.
In step 1 of the wizard, in the parameter section, replace the S3ResourceBucket parameter with the name of your demo-code bucket (the S3 bucket where you uploaded the demo code). 
Retain the remaining default settings.

3. Acknowledge the capabilities check, and create the stack.
This stack launches two additional stacks: one creates an AWS Cloud9 instance and the other creates the lab application called the Polly Notes.

Task 3: Verifying your environment settings
After the stack is completed, make sure that the following resources were created so that you can help students with the demo:
- Lambda functions – All five lambda functions (Python) with tracing enabled.
- API Gateway resources
- AWS Cloud9 instance – Contains the code necessary to host the application. You can use the code snippets in your demos.
- Website– Website URL for your Polly Notes application. 
-- User name: student
-- Password: student
