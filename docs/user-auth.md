# User Authentication

## User Login
  <strong>Page:</strong> User Login   
<strong>Method:</strong> POST   
<strong>Name:</strong> User Login   
<strong>Description:</strong> Login For User    
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/auth/login     

<strong>Request:</strong>

    Headers CSRF:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"

    Headers Token:  
    "Authorization": "Bearer ${token}", (type: string, required: true, description: Bearer token)
    
    Parameters:
    "username": "tester", (type: string, required: true, description: Username of user)
    "password": "password" (type: string, required: true, description: Password of user)
    "browser_id": "3820c94b-b630-403e-a064-d3137488845f" (type: string:uuid V4, optional: true, description: Browser id for user retrive from cookie)
    
<strong>Responses:</strong>


    SUCCESS:

        Status: 200 Ok
    

        Example:
        {
          "token": "37|Yt6oeZamDOqKdDPGUPDT80Xulp6KPDvX32C4BlvV",
          "user": {
              "id": 1,
              "first": "tester1",
              "last": "tester2",
              "phone": "55-80-27-89-89",
              "username": "tester",
              "created_at": "2021-04-02T02:53:46.000000Z",
              "updated_at": "2021-04-02T02:53:46.000000Z"
          },
          "browser_id": "37646037-8230-4905-8250-cfff968e1714"
      }



    ERRORS:

        Status: 422 Unprocessable Entity

        Example:

        {
          "error": {
              "password": [
                  "The password field is required."
              ]
          },
          "message": "Failed validation"
        }


        Status: 422 Unprocessable Entity

        Example:

        {
          "error": [],
          "message": "Invalid Credentials"
        }
        

## User Two Factor Authentication Code Verify
  <strong>Page:</strong> User Two Factor Authentication Code Verify   
<strong>Method:</strong> POST   
<strong>Name:</strong> User Two Factor Authentication Code    
<strong>Description:</strong> Two Factor Authentication Code For LOGGED User    
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/auth/code-verify     

<strong>Request:</strong>

    Headers CSRF:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"

    Headers Token:  
    "Authorization": "Bearer ${token}", (type: string, required: true, description: Bearer token)

    Parameters:
    "code": "12345", (type: string, required: true, description: 5 Digit verification code ),
    "browser_id": "3820c94b-b630-403e-a064-d3137488845f" (type: string:uuid V4, optional: true, description: Browser id for subdomain user retrive from cookie)
   
<strong>Responses:</strong>


    SUCCESS:
        Status: 200 Ok
    

        Example:
        {
          "data": [
            {
            "token": "10|fQAK7wdQkTf44RUuDZWRfIyw3qGv5hQvIWOLHI97",
            "user": {
              "id": 3,
              "name": "tester",
              "username": "tester",
              "created_at": "2021-03-27T18:06:27.000000Z",
              "updated_at": "2021-03-27T18:06:27.000000Z"
              }
            }
          ]
        }



    ERRORS:

        Status: 422 Unprocessable Entity

        Example:

        {
          "error": {
              "code": [
                  "The code field is required."
              ]
          },
          "message": "Failed validation"
        }


        Status: 422 Unprocessable Entity

        Example:

        {
          "error": [],
          "message": "Invalid Code"
        }

## Remember User Session
  <strong>Page:</strong> Remember User Session    
<strong>Method:</strong> POST   
<strong>Name:</strong> User Remember Session    
<strong>Description:</strong> CHANGE User Session Remember (two-factor-authentication needed)
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/auth/remember    

<strong>Request:</strong>

    Headers CSRF:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"

    Headers Token:  
    "Authorization": "Bearer ${token}", (type: string, required: true, description: Bearer token)

    Parameters:
    "is_remembered": 1, (type: boolean, required: true, description: 1 for remember and 0 for do not remember session),
    "browser_id": "3820c94b-b630-403e-a064-d3137488845f" (type: string:uuid V4, optional: true, description: Browser id for subdomain user retrive from cookie)
    
<strong>Responses:</strong>
    SUCCESS:
        Status: 200 Ok
    

        Example:
        {
          "message": "Session changes saved"
        }

    ERRORS:

        Status: 422 Unprocessable Entity

        Example:

        {
          "error": {
              "is_remembered": [
                  "The is remembered field is required."
              ]
          },
          "message": "Failed validation"
        }


        Status: 422 Unprocessable Entity

        Example:

        {
          "error": {
              "browser_id": [
                  "The selected browser id is invalid."
              ]
          },
          "message": "Failed validation"
      }
        

## User Register
  <strong>Page:</strong> User Register    
<strong>Method:</strong> POST   
<strong>Name:</strong> Register   
<strong>Description:</strong> Register For New User   
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/auth/register    
  
<strong>Request:</strong>

    Headers CSRF:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"

    Headers Token:  
    "Authorization": "Bearer ${token}", (type: string, required: true, description: Bearer token)

    Parameters:
    "first": "tester", (type: string, required: true, description: First name of user of main subdomain )
    "last": "tester", (type: string, required: true, description: Last name of user of main subdomain )
    "username": "tester", (type: string, required: true, description: Username of   main subdomain )
    "password": "password" (type: string, required: true, description: Password for subdomain user)
    "password_confirmation": "password_confirmation" (type: string, required: true, description: Password confirmation for subdomain user)
    "phone": "5580278960" (type: string, required: true, description: Password confirmation for subdomain user)
    "config": "{"permisions":{"ability_1":["module1:index","module1:create","module1:show","module1:update","module1:delete"],"ability_2":["module1:create","module1:show","module1:update","module2:index","module2:create","module2:show","module2:update","module2:delete"],"ability_3":["module1:index"]},"roles":["admin"]}", (type: json, optional: true, description: abilities and permisions for new user )

<strong>Responses:</strong>


    SUCCESS:
        Status: 200 Ok
    

        Example:
        {
          "data": [
            {
            "token": "10|fQAK7wdQkTf44RUuDZWRfIyw3qGv5hQvIWOLHI97",
            "user": {
              "id": 3,
              "name": "tester",
              "username": "tester",
              "created_at": "2021-03-27T18:06:27.000000Z",
              "updated_at": "2021-03-27T18:06:27.000000Z"
              }
            }
          ]
        }

    ERRORS:

        Status: 422 Unprocessable Entity

        Example:

        {
          "error": {
              "password": [
                  "The password field is required."
              ]
          },
          "message": "Failed validation"
        }


        Status: 422 Unprocessable Entity

        Example:

        {
          "error": [],
          "message": "Invalid Credentials"
        }

## User Logout
  <strong>Page:</strong> User Logout    
<strong>Method:</strong> POST   
<strong>Name:</strong> Tenancy Logout    
<strong>Description:</strong> Logout For User   
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/auth/logoout     

<strong>Request:</strong>

    Headers CSRF:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"

    Headers Token:  
    "Authorization": "Bearer ${token}", (type: string, required: true, description: Bearer token)
  
<strong>Responses:</strong>
    SUCCESS:
        Status: 200 OK

    ERRORS:
        Status: 500 Internal Server Error

## User Info
  <strong>Page:</strong> User Info   
<strong>Method:</strong> POST   
<strong>Name:</strong> Register   
<strong>Description:</strong> Info for Logged User (two-factor-authentication needed)    
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/user    
  
<strong>Request:</strong>

    Headers CSRF:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"

    Headers Token:  
    "Authorization": "Bearer ${token}", (type: string, required: true, description: Bearer token)

<strong>Responses:</strong>


    SUCCESS:
        Status: 200 Ok
    

        Example:
        {
          "user": {
            "id": 1,              
            "username": "Sergio",
            "created_at": "2021-04-02T02:53:46.000000Z",
            "updated_at": "2021-04-02T02:53:46.000000Z"
          }
        }

    ERRORS:

        Status: 404 Not Found 


        Status: 423 Locked
    

        Example:
        {
          "message": "Verification code has been sent",
          "errors": []
        }
        
    
