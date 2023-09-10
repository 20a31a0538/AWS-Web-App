
# AWS Web App

Accomplished the design and development of a fully functional end-to-end AWS web application by leveraging AWS Amplify, AWS Lambda, AWS API Gateway, AWS DynamoDB, and AWS IAM, showcasing expertise in cloud architecture and serverless computing.


## Roadmap

- A way to create/host a webpage 
- A way to invoke the math functionality.
- A way to do some math.
- Somewhere to store the result of math.
- A way to handle the permissions. 




## Services Used
- AWS Amplify 
- AWS Lambda
- AWS DynamoDB
- AWS IAM 
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/4c09d029-ea0f-4f1f-a832-9909c8d8dd33)

## Step 1: A way to create/host a web page  AWS Amplify
- used to build and host a website. We will use the text editor to create an index.html file on my local machine.
Search for AWS Amplify. Click on Get started

- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/82949d36-25fc-4b30-9f33-d3a08504ff9d)

## Step 2: To do math  AWS Lambda
- To do math  AWS Lambda: a bit code code that runs when we trigger(serverlessly).
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/db464121-04f0-48db-9af3-97172bbc3c79)

- Lambda function with source code of power of numbers.
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/34b7f7f1-5b5d-4aa7-8d08-4387efbd71d9)

- Click on ctrl + s, then deploy.
Now, test it
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/c8fb6ed4-8c42-4361-bc9e-88c4ae81c251)

- Now, we need to do that to invoke the math functionality(invoke lambda function)  Aws API Gateway  core services which helps to build our own API(http, REST, Socket).
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/9a8d71be-a86a-4de5-9783-7d81f7ccfb62)

## Step 3:
- Open AWS API Gateway and build REST API.
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/35bc7fb2-31e0-4c0a-9547-28cf7315736d)

- Click on Create API.
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/da213d3c-c918-4792-bca3-7a96494afa60)

- Now create a method called POST(the user is sending data for two numbers).
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/e946757d-4155-471a-8916-7d8a4be84ff0)

- Click on the tick mark.
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/cbd566ba-3319-4b46-9250-179d9dc4a50e)

- Integration type is lambda function.
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/b7c62770-6eb5-421a-b52c-9c5405e8794d)

- Click on save. Here, we are giving permission to API Gateway permission to invoke your Lambda function.
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/6278d751-e961-4845-969d-c07e55eebcf4)

- Flow of integration:
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/99c0899e-6a17-48df-b734-279cddf19765)

- One more thing, we need to do is Enable CORES() Basically, it allows web apps running in one origin or domain to access resources on different origins or domains. My application runs on one domain called amplify and another domain called lambda function.
Click on post(actions) --> click Enable
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/8a03a7f8-dd2d-44b4-965b-c333d6152964)

- Now, let us deploy it out. Go to actions.
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/dbae8180-9546-4d62-8b44-1fc1780cb349)

- API Gateway URL: https://hj8ywcpwo3.execute-api.ap-south-1.amazonaws.com/dev
Now, test it out. Go to resources then POST then resources body.
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/b35dbdb8-9e00-4cfe-8fec-df4c8c51c93a)

- Result:
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/099d00d4-c04b-40db-bdfc-7381c7e41809)


## Step 4: To store the result in the database
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/003b6701-f87d-416d-bef7-f1011c50f34f)

- We are using dynamoDB which is a NoSQL database. It is lighter than the Relation Database. We need to set up schema etc.
Using IAM  we need to give our lambda function  permission to write to a database.
Now, Create a DynamoDB Table :
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/1b068f54-bfe5-4c92-91d7-8d9dd5bc2549)

- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/6e5bc9f0-a002-4670-a4cd-407635c421f6)

- Save the ARN : arn:aws:dynamodb:ap-south-1:039638597321:table/PowerOfNumberTable
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/5996ed16-1d65-4ee2-aa32-985d96db9e00)

- Now, we are going to give lambda function permissions.
Go to lambda function >> configuration >>  permissions >> execute role(give permissions using IAM Role or open in new tab )
Now create inline policy >> add ARN(which gives permission to lambda function)

- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/079de08d-75b4-40a9-9b63-b106893d5eb2)

Create policy:
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/7d6e38ef-c8a9-4b63-aa30-64fd6d1b26c0)

- UPDATE the lambda function
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/a41d65de-84f9-4033-8ca3-3b3c63c7ba6e)

- Result:
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/59b45e28-286a-43b8-ac9e-05326f043525)

- Now, go to dynamo DB >> Explore the table 
The result was stored in dynamo DB
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/5390fbba-ce51-4621-afa1-2e9107324daa)




## Step 5: Deployment
- Update the index.html(link the API URL)and deploy in the amplify
- Code:
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/caa9f6f8-5537-44e7-8ee2-ea0a48480088)

- After deployment:
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/2ada5aed-fc63-40d9-9bd5-c766bddd560c)

- Result:
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/67fdb78d-9034-40e9-91ef-7d83e587e491)


