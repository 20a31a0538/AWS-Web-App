
# AWS Web App

Accomplished the design and development of a fully functional end-to-end AWS web application by leveraging AWS Amplify, AWS Lambda, AWS API Gateway, AWS DynamoDB, and AWS IAM, showcasing expertise in cloud architecture and serverless computing.


## Roadmap

- A way to create/host a webpage 
- A way to invoke the math functionality.
- A way to do the some math.
- Somewhere to store the result of math.
- A way to handle the permissions. 




## Services Used
- AWS Amplify 
- AWS Lambda
- AWS DynamoDB
- AWS IAM 
![App Screenshot](![image](![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/a37397c7-0b81-4e4e-b477-ee4c95bc6293)
))
## Result

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)


## Step 1:
- A way to create/host a web page  AWS Amplify : used to build and host a website. And we will use text editor to create a index.html file in my local machine.
Search for AWS Ampilfy. Click on Get started

- 
## Step 2:
- To do math  AWS Lambda : a bit code code that runs when we trigger(serverlessly).
- ![image](https://github.com/20a31a0538/AWS-Web-App/assets/110081197/db464121-04f0-48db-9af3-97172bbc3c79)

- Lambda function with source code of power of numbers.
- sc
- Click on ctrl + s, then deploy.
Now, test it
- sc
- Now, we need to do that to invoke the math functionality(invoke lambda function)  Aws API Gateway  core services which helps to build our own API(http, REST, Socket).
- sc
## Step 3:
- Open AWS API Gateway and build REST API.
- sc
- Click on create API.
- sc
- Now create a method called POST(user is sending data for two numbers).
- sc
- Click on tick mark.
- sc
- Integration type is lambda function.
- sc
- Click on save. Here, we are giving permission to API Gateway permission to invoke your Lambda function.
- sc
- Flow of integration:
- sc
- One more thing, we need to do is that Enable CORES() basically, it does to allows web app running in one origin or domain able to access resources on different origin or domain. My application running on one domain called amplify and other domain called lambda function.
Click on post(actions) --> click Enable
- sc
- Now, let us deploy it out. Go to actions.
- sc
- API Gateway URL: https://hj8ywcpwo3.execute-api.ap-south-1.amazonaws.com/dev
Now, test it out. Go to resources then POST then resources body.
- sc
- Result:
- sc

## Step 4:
- To store the result at database
- sc
- We are using dynamoDB which is NoSQL database.It is lighter than Relation Database. We need to setup schema etc.
Use IAM  we need to give our lambda function  permission to write to a database.
Now, Create a DynamoDB Table :
- sc
- sc
- Save the ARN : arn:aws:dynamodb:ap-south-1:039638597321:table/PowerOfNumberTable
- sc
- Now, we are going to give lambda function permissions.
Go to lambda function >> configuration >>  permissions >> execute role(give permissions using IAM Role or open in new tab )
Now create inline policy >> add ARN(which gives permission to lambda function)

- sc
Create policy:
- sc
- UPDATE the lambda function
- sc
- Result:
- sc
- Now, go to dynamoDB >> Explore table 
Result was stored in dynamo DB
- sc



## Step 5:
- Update the index.html(link the API URL)and deploy in the ampilfy
- Code:
sc
- After deployment:
sc
- Result:
sc
