# Week 0 — Billing and Architecture

Types of design :
1. Concenptual Design
      Organizes & defines conecpets & rules
      Napkin design
2. Logical Design 
    Defines hows the system should be implemented
    Environemnt without actual names or sizes 
3. Physical Design
     Representation of the actual thing 
    Ip addreses , Ec2 Addresses

AWS set up:
 1.Create biling Alarm 
 2.Create AWS Budgets 
 3. Used aws cloud shell :
      Commands: 
         aws sts get-caller-identity

Napkin Design :
![Napkin](https://github.com/OrinaOisera/aws-bootcamp-cruddur-2023/blob/main/WhatsApp%20Image%202023-02-20%20at%2018.39.10.jpeg)


Cruddur Logical Dagram:
Lucid Chart: https://lucid.app/lucidchart/06686680-ec42-4960-b88e-ace317b2cefd/edit?viewport_loc=-870%2C203%2C3928%2C1730%2C0_0&invitationId=inv_07da2874-c13b-42dc-be6d-0337c0e2e0cd

Architecture diagram:![Cruddur](https://github.com/OrinaOisera/aws-bootcamp-cruddur-2023/blob/main/aws_crddur_app.png)

AWS Billing commands:
aws budgets create-budget \
    --account-id $AWS_ACCOUNT_ID\
    --budget file://aws/json/budget.json \
    --notifications-with-subscribers file://aws/json/budget-notifications-with-subscribers.json
    
   AWS sns :
aws sns subscribe \
    --topic-arn arn:aws:sns:us-east-1:815724397517:billing-alarm \
    --protocol email \
    --notification-endpoint oiseraorina@gmail.com
    
   AWS cloud watch:
 aws cloudwatch put-metric-alarm --cli-input-json file://aws/json/alarm_config.json
    
