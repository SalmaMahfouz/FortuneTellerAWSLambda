# FortuneTellerAWSLambda
A simple fortune teller app using AWS Lambda &amp; AWS API GW
Steps:
1) Go to AWS Lambda:
   Choose "Author from Scratch"
   Give the funtion a name & choose Python 3.11
   ![image](https://github.com/SalmaMahfouz/FortuneTellerAWSLambda/assets/56725273/0bdbc517-345e-415b-a0c2-dfecdc9db5e3)
2) Add the code in the Lambda Function:
   It is a simple function, that generates random numbers, and based on the random generated, an answer is given "yes, no, maybe"
   ![image](https://github.com/SalmaMahfouz/FortuneTellerAWSLambda/assets/56725273/c7035709-481f-46eb-ac4f-c9ceb63c2da2)
3) Click deploy, then Test
   The test result should be something like the below:
   ![image](https://github.com/SalmaMahfouz/FortuneTellerAWSLambda/assets/56725273/796e6169-a501-4bfb-a7d7-40033b5811b6)
   by clicking on "Test" the message will keep chaning based on the random number generated.
4) Then now we need to create the API
5) Go to API Gateway service, and click on HTTP API
6) Add the integration to be "Lambda" & choose the name of the function, set an API Name, then click next.
7) Choose the method "GET"
8) Go to "Routes", "Configure" to add a parameter.
9) Mapping type will be "All incoming requests", parameter to modify will be "querystring.question", modification type "Append", value "$request.querystring.question"
    ^ "question" could be changed with whatever word.
10) You need to take a note of this, because this what will we add in the Invoking URL:
    ![image](https://github.com/SalmaMahfouz/FortuneTellerAWSLambda/assets/56725273/b0867c67-ccc3-48b0-916f-29ea21bf5747)
11) go to APIs, click on the fortune teller API, there is no need to click deploy, because "auto deploy" was enabled when we created the API.
12) Take the invoke URL, paste it in the browser, and add the following: /FortuneTellerApp?question="Should I go out today?"
    The invoke URL would be something like this: https://3rreln8oee.execute-api.us-east-1.amazonaws.com/dev
    so the full URL would be https://3rreln8oee.execute-api.us-east-1.amazonaws.com/dev/FortuneTellerApp?question="Should I go out today?"
13) You will get an answer like the below:
    ![image](https://github.com/SalmaMahfouz/FortuneTellerAWSLambda/assets/56725273/0da2728a-7346-4f2e-9b26-e2cee25458ae)
    By refershing , and changing the question, we should receive random answers to the question.



   
   
   
