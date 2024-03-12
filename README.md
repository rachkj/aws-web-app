# Steps Followed:

## AWS Amplify:
1. Create an index.html file which has some basic data (index-basix.html file containes this data). <br />
2. Save it and create a zip version of this file: index.zip.  <br />
3. Select AWS Amplify on the Console and create 'New App'.  <br />
4. Select 'Deploy without Git Provider', and give a name: "powerOfMath".  <br />
5.Give environment as "dev" and drag and drop the index.zip.  <br />
6. Wait until deployment is successful. Click on the 'Domain' URL to see the webpage launced using Amplify.  <br />

## AWS Lambda:
1. Select AWS Lambda from the console and create a new function. Give a function name: 'poweOfMathFunction' and select the runtime to be Python. Click on 'Create Function'. In the code section add the code whats present in lambda-basic.py  <br />
2. Save the code and then click on 'Deploy'.  <br />
3. Create a test event. Give a name and use the JSON in the format:  <br />
   {  <br />
   "base": 2,  <br />
   "exponent": 3  <br />
   }  <br />
4. Click on Test and see if you get a 200 response with the result.  <br />

 ## API Gateway:  <br />
 1. Select API Gateway on the AWS Console and click on 'Create API'.  <br />
 2. Craete a REST API with a name: powerOfMathAPI. <br />
 3. Create method POST. Select Lambda function and select the function previously created. Click on save. <br />
 4. Click on 'Enable Cors'. This allows applications in different origins or domains to access each other. Example: web application on Amplify and Lambda function might be on two different domains. <br />
 5. Deploy API with a stage name and then click on 'Deploy'. Copy the 'Invoke URL" that shows up on screen. <br />
 6. Click on 'Test' for POST and enter:
    {  <br />
   "base": 2,  <br />
   "exponent": 3  <br />
   }  <br />
 7. Click on Test and see if you get a 200 response with the result.  <br />

