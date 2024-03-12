# Steps Followed:

## AWS Amplify:
1. Create an index.html file which has some basic data such as: <br />
  <!DOCTYPE html> 
  <html> 
  <head>  
      <meta charset="UTF-8">  
      <title>To the Power of Math!</title>  
  </head> 
  
  <body> 
      To the Power of Math!  
  </body>  
  </html> 
2. Save it and create a zip version of this file: index.zip.  <br />
3. Select AWS Amplify on the Console and create 'New App'.  <br />
4. Select 'Deploy without Git Provider', and give a name: "powerOfMath".  <br />
5.Give environment as "dev" and drag and drop the index.zip.  <br />
6. Wait until deployment is successful. Click on the 'Domain' URL to see the webpage launced using Amplify.  <br />

## AWS Lambda:
1. Select AWS Lambda from the console and create a new function. Give a function name: 'poweOfMathFunction' and select the runtime to be Python. Click on 'Create Function'. In the code section add the below code:  <br />
  # import the JSON utility package  <br />
  import json  <br />
  # import the Python math library  <br />
  import math  <br />
  
  # define the handler function that the Lambda service will use an entry point  <br />
  def lambda_handler(event, context):  <br />
  
  # extract the two numbers from the Lambda service's event object  <br />
      mathResult = math.pow(int(event['base']), int(event['exponent']))  <br />
  
      # return a properly formatted JSON object  <br />
      return {  <br />
      'statusCode': 200,  <br />
      'body': json.dumps('Your result is ' + str(mathResult))  <br />
      }  <br />
2. Save the code and then click on 'Deploy'.  <br />
3. Create a test event. Give a name and use the JSON in the format:  <br />
   {  <br />
   "base": 2,  <br />
   "exponent": 3  <br />
   }  <br />
4. Click on Test and see if you get a 200 response with the result.  <br />

 ## API Gateway:  <br />
 1. Select API Gateway on the AWS Console and click on 'Create API'.  <br />

