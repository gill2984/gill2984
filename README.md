# Skateboard Rest API
#### Created by Kevin Gill

### General Approach
Created in AWS API Gateway, coded in Node.js using Lambda, used DynamoDB (NoSQL) for the database.

Using PostMan, Get, Post, Delete, Patch commands can be used. 

Information is sent and received using JSON.

All Logging in managed by AWS CloudWatch.


**Use Postman (Highly Recommended)**

**Send all requests through Request Body as raw JSON**

### Website URL
https://cqsiq1u6il.execute-api.us-east-2.amazonaws.com/pro/

"{"message":"Missing Authentication Token"}" is the default result.

## How to Perform Requests:

### POST Request
Used to create new skateboards

**Send all requests through Request Body as raw JSON**

https://cqsiq1u6il.execute-api.us-east-2.amazonaws.com/pro/skateboard
Need to use Postman to submit Post request, in JSON Body

#### Sample POST Request Format
```
{
    "skateboardId":"random 5 digit number",
    "owner": “First Name",
    "brand": "skateboard brand",
    "color": "color",
    "condition": “pick 1 condition: Like New, Great, Good, Fair, Poor",
    "stat": "Either Available or Unavailable",
    "image": "image URL"
}        
```

#### Example POST Request
```
{
    "skateboardId":"10044",
    "owner": "Luke",
    "brand": "Element",
    "color": "Red",
    "condition": "Good",
    "stat": "Available",
    "image": "https://drive.google.com/file/d/1YzgwAfeTzEAUMpOEnQQrDmv9T3DZMZ5/view?usp=sharing"
}        
```
### GET Request
Used to get Skateboard Information that is already stored in the database, Key required to access data. 
https://cqsiq1u6il.execute-api.us-east-2.amazonaws.com/pro/skateboard

Key = skateboardId
Key Value = 5 digit assigned number. (Can test using: 10011, 10022, 10033, 10044)

Sample Get Request URL
https://cqsiq1u6il.execute-api.us-east-2.amazonaws.com/pro/skateboard?skateboardId=10011


### PATCH Request
Key function is to change skateboard status available to unavailable or vice versa. Can also be used to change 1 parameter.
https://cqsiq1u6il.execute-api.us-east-2.amazonaws.com/pro/skateboard
**Send Request through Request Body as raw JSON**


#### Send Request as shown below 
```
{
    "skateboardId":"5 digit code",
    "updateKey": "stat",
    "updateValue": "Unavailable"
}
```

### GET Request
Use following link to get access to all stored skateboards
https://cqsiq1u6il.execute-api.us-east-2.amazonaws.com/pro/skateboards

### DELETE Request
Used to delete skateboards
https://cqsiq1u6il.execute-api.us-east-2.amazonaws.com/pro/skateboard
Send Request through JSON Body

#### Send Request as shown below 
```
{
    "skateboardId": "5 digit skateboardId of which skateboard you wish to delete"
}
```
