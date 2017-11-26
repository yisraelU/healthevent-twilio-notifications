## health-twilio-notifications

A simple python program that is invoked for all health events that occur in your account, then sends a text message to a number specified in your lambda environment variable. 


### Prerequisites
- Setup Twilio account and number [here](http://twilio.com/user/account) to obtain Account SID, Auth Token and a from phone number.

### The SAM template creates the following resources:
- 1 Lambda Function, python 2.7 with 4 environment variables
- 1 IAM Role with 1 Managed Policy
- 1 Lambda Trigger, that allows health related Cloudwatch Events to invoke Lambda.



### High level flow
Once set up, this would work as follows:

- When a health related event shows up in your account(PHD). Cloudwatch event captures it and invokes the Lambda function
- The Lambda function uses the environment variables configured to communicate with twilio to send the text message with the event description and the URL of the PHD event


### Additional Considerations/Limitations

- For voice based notifications refer to this [blog post](https://aws.amazon.com/blogs/ai/phone-call-alerts-on-aws-account-security-events-using-amazon-polly)


