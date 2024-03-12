# Steps Followed:

## AWS Amplify:
1. Create an index.html file which has some basic data such as: <br />
  <!DOCTYPE html>  <br />
  <html>  <br />
  <head>  <br />
      <meta charset="UTF-8">  <br />
      <title>To the Power of Math!</title>  <br />
  </head>  <br />
  
  <body>  <br />
      To the Power of Math!  <br />
  </body>  <br />
  </html>  <br />
2. Save it and create a zip version of this file: index.zip.  <br />
3. Select AWS Amplify on the Console and create 'New App'.  <br />
4. Select 'Deploy without Git Provider', and give a name: "powerOfMath".  <br />
5.Give environment as "dev" and drag and drop the index.zip.  <br />
6. Wait until deployment is successful. Click on the 'Domain' URL to see the webpage launced using Amplify.  <br />

## AWS Lambda:
1. Select AWS Lambda from the console and create a new function. Give a function name: 'poweOfMathFunction' and select the runtime to be Python. Click on 'Create Function'. In the code section add the below code:
  # import the JSON utility package
  import json
  # import the Python math library
  import math
  
  # define the handler function that the Lambda service will use an entry point
  def lambda_handler(event, context):
  
  # extract the two numbers from the Lambda service's event object
      mathResult = math.pow(int(event['base']), int(event['exponent']))
  
      # return a properly formatted JSON object
      return {
      'statusCode': 200,
      'body': json.dumps('Your result is ' + str(mathResult))
      }
2. Save the code and then click on 'Deploy'
3. Create a test event. Give a name and use the JSON in the format:
   {
   "base": 2,
   "exponent": 3
   }
4. Click on Test and see if you get a 200 response with the result.

 ## API Gateway:
 1. Select API Gateway on the AWS Console and click on 'Create API'

