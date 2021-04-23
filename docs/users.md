# Users 

## User List
  <strong>Page:</strong> User List   
<strong>Method:</strong> POST   
<strong>Name:</strong> Register   
<strong>Description:</strong> List of users User   
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/users    
  
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
          "data": [
              {
                  "id": 1,
                  "first": null,
                  "last": null,
                  "phone": null,
                  "username": "Sergio",
                  "created_at": "2021-04-02T02:53:46.000000Z",
                  "updated_at": "2021-04-02T02:53:46.000000Z"
              },
              {
                  "id": 2,
                  "first": null,
                  "last": null,
                  "phone": null,
                  "username": "tester",
                  "created_at": "2021-04-02T02:53:46.000000Z",
                  "updated_at": "2021-04-02T02:53:46.000000Z"
              }
          ]
        }

    ERRORS:

        Status: 404 Not Found 

