# serverless-plugin-api-gateway-auth
Serverless plugin supporting AWS_IAM authorizer on API Gateway method

Adds the ability to configure AWS_IAM for your API Gateway endpoints, and "Invoke with caller credentials"

## Usage
register plugin:
```YAML
plugins:
  - serverless-plugin-api-gateway-auth
```

enable IAM authentication:
```YAML 
    myFuncGetItem:
      handler: myFunc.get
      name: ${self:provider.stage}-myFunc-get-item
      memorySize: 128
      events:
        - http:
            method: GET
            path: mypath
            cors: true
            useIAMAuth: true
            invokeWithCallerCredentials: true
```
