# Tenancy Authentication

## Tenancy Login
  <strong>Page:</strong> Tenancy Login    
  <strong>Method:</strong> POST     
  <strong>Name:</strong> Tenancy Login      
  <strong>Description:</strong> Login for main domain     
  <strong>Endpoint:</strong> http://{{domain}}/auth/login       

<strong>Request:</strong>

    Headers CSRF:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"

    Headers Token:  
    "Authorization": "Bearer ${token}", (type: string, required: true, description: Bearer token)

    Parameters:
    "username": "tester", (type: string, required: true, description: Username of   main domain )
    "password": "password" (type: string, required: true, description: Password for domain user)

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


        Status: 422

        Example:

        {
          "error": [],
          "message": "Invalid Credentials"
        }

## Tenancy Register
  <strong>Page:</strong> Tenancy Register   
  <strong>Method:</strong> POST   
  <strong>Name:</strong> Tenancy Register    
  <strong>Description:</strong> Register For Tenancy    
  <strong>Endpoint:</strong> http://{{domain}}/auth/register    

<strong>Request:</strong>

    Headers CSRF:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"

    Headers Token:  
    "Authorization": "Bearer ${token}", (type: string, required: true, description: Bearer token)

    Parameters:
    "first": "tester", (type: string, required: true, description: First name of user of main domain )
    "last": "tester", (type: string, required: true, description: Last name of user of main domain )
    "username": "tester", (type: string, required: true, description: Username of   main domain )
    "password": "password" (type: string, required: true, description: Password for domain user)
    "password_confirmation": "password_confirmation" (type: string, required: true, description: Password confirmation for domain user)
    "phone": "5580278960" (type: string, required: true, description: Password confirmation for domain user)

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


        Status: 422

        Example:

        {
          "error": [],
          "message": "Invalid Credentials"
        }


## Tenancy Logout
  <strong>Page:</strong> Tenancy Logout   
<strong>Method:</strong> POST   
<strong>Name:</strong> Tenancy Logout    
<strong>Description:</strong> Logout For Tenancy    
<strong>Endpoint:</strong> http://{{domain}}/auth/logout    

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
