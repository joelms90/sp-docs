
## LOCATIONS
  <strong>Page:</strong> LOCATIONS    
<strong>Method:</strong> POST   
<strong>Name:</strong> New LOCATION   
<strong>Description:</strong> ADD New LOCATION    
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/location     

<strong>Request:</strong>

    Headers:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"

    Parameters:
    "name": "Michigan Clinic", (type: string, required: true, description: Name of location )
    "street": "Luettgen Lock", (type: string, optional: true, description: Street of location )
    "city": "Port", (type: string, optional: true, description: City of location )
    "state": "Michigan", (type: string, optional: true, description: State of location )
    "zip": "07110", (type: string, optional: true, description: Zip code of location )
    "phone": "+1-654-379-7757", (type: string, optional: true, description: Phone of location )
    <strong>"email</strong>": "lemke.julianne@aufderhar.com", (type: string, optional: true, Description: email of location )
    "timezone": "Africa/Malabo", (type: string, required: true, description: Timezone of location )
    "tax_id": "92411886", (type: string, optional: true, description: Tax id of location )
    "ndi_number": "95756910", (type: string, optional: true, description: NDI number of location )
  

<strong>Responses:</strong>
    SUCCESS:
        Status: 200 Ok
    

        Example:
        {
          "data": [
                  "id": 1,
                  "name": "Michigan Clinic",
                  "street": "Luettgen Lock",
                  "city": "Port",
                  "state": "Michigan",
                  "zip": "07110",
                  "phone": "+1-654-379-7757",
                  "email": "lemke.julianne@aufderhar.com",
                  "timezone": "Africa/Malabo",
                  "tax_id": "92411886",
                  "ndi_number": "95756910",
                  "created_by": 1,
                  "created_at": "2021-04-02T02:53:46.000000Z",
                  "updated_at": "2021-04-02T02:53:46.000000Z"
          ]
        }

    ERRORS:

        Status: 404 Not Found## LOCATIONS        ## LOCATIONS
          <strong>Page:</strong> LOCATIONS        ## LOCATIONS    
<strong>Method:</strong> GET
<strong>Name:</strong> GET LOCATIONS
<strong>Description:</strong> GET LOCATIONS
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/location 

<strong>Request:</strong>

    Headers:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"  
    

<strong>Responses:</strong>
    SUCCESS:
        Status: 200 Ok
    
        Example:
        {
          "data": {
            [
              "id": 1,
              "name": "Michigan Clinic",
              "street": "Luettgen Lock",
              "city": "Port",
              "state": "Michigan",
              "zip": "07110",
              "phone": "+1-654-379-7757",
              "email": "lemke.julianne@aufderhar.com",
              "timezone": "Africa/Malabo",
              "tax_id": "92411886",
              "ndi_number": "95756910",
              "created_by": 1,
              "created_at": "2021-04-02T02:53:46.000000Z",
              "updated_at": "2021-04-02T02:53:46.000000Z"
            ]
          },
          {
            [
              "id": 2,
              "name": "Michigan Clinic2",
              "street": "Luettgen Lock",
              "city": "Port",
              "state": "Michigan",
              "zip": "07123",
              "phone": "+1-654-379-7758",
              "email": "lemke.julianne@aufderhar.com",
              "timezone": "Africa/Malabo",
              "tax_id": "92411836",
              "ndi_number": "95256910",
              "created_by": 1,
              "created_at": "2021-04-02T02:53:46.000000Z",
              "updated_at": "2021-04-02T02:53:46.000000Z"
            ]
          }
        }

    ERRORS:
        Status: 404 Not Found 

## LOCATIONS
  <strong>Page:</strong> LOCATIONS    
<strong>Method:</strong> PATCH
<strong>Name:</strong> UPDATE LOCATION
<strong>Description:</strong> UPDATE LOCATION
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/location/{{id}}

<strong>Request:</strong>

    Headers:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"  
    
    Parameters:
    "name": "Michigan Clinic", (type: string, required: true, description: Name of location )
    "street": "Luettgen Lock", (type: string, optional: true, description: Street of location )
    "city": "Port", (type: string, optional: true, description: City of location )
    "state": "Michigan", (type: string, optional: true, description: State of location )
    "zip": "07110", (type: string, optional: true, description: Zip code of location )
    "phone": "+1-654-379-7757", (type: string, optional: true, description: Phone of location )
    <strong>"email</strong>": "lemke.julianne@aufderhar.com", (type: string, optional: true, Description: email of location )
    "timezone": "Africa/Malabo", (type: string, required: true, description: Timezone of location )
    "tax_id": "92411886", (type: string, optional: true, description: Tax id of location )
    "ndi_number": "95756910", (type: string, optional: true, description: NDI number of location )
    
<strong>Responses:</strong>
    SUCCESS:
        Status: 204 Ok

    ERRORS:
        Status: 404 Not Found 

<strong>Method:</strong> GET
<strong>Name:</strong> SHOW LOCATION
<strong>Description:</strong> SHOW LOCATION
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/location/{{id}}

<strong>Request:</strong>

    Headers:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"  
    
    Parameters:
    "id": 1, (type: string, required: true, description: Id of location )
    
<strong>Responses:</strong>
    SUCCESS:
        Status: 204 Ok

        Example:
        {
          "data": [
                  "id": 1,
                  "name": "Michigan Clinic",
                  "street": "Luettgen Lock",
                  "city": "Port",
                  "state": "Michigan",
                  "zip": "07110",
                  "phone": "+1-654-379-7757",
                  "email": "lemke.julianne@aufderhar.com",
                  "timezone": "Africa/Malabo",
                  "tax_id": "92411886",
                  "ndi_number": "95756910",
                  "created_by": 1,
                  "created_at": "2021-04-02T02:53:46.000000Z",
                  "updated_at": "2021-04-02T02:53:46.000000Z"
          ]
        }

    ERRORS:
        Status: 404 Not Found 

## ROLES            
  <strong>Page:</strong> ROLES                
<strong>Method:</strong> POST   
<strong>Name:</strong> New ROLE   
<strong>Description:</strong> ADD New ROLE    
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/role     

<strong>Request:</strong>

    Headers:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"

    Parameters:
    "group": "Josianne Haley", (type: string, required: true, description: Group of role )
    "slug": "nostrum-aliquid-mollitia-eum-vel-ea-velit-ipsam", (type: string, required: true, description: Slug for role )
    "name": "Pauline Schroeder", (type: string, required: true, description: Name of role )


<strong>Responses:</strong>
    SUCCESS:
        Status: 200 Ok

        Example:
        {
          "data": [
            "id" => 1
            "group" => "Josianne Haley"
            "slug" => "nostrum-aliquid-mollitia-eum-vel-ea-velit-ipsam"
            "name" => "Pauline Schroeder"
            "updated_at" => "2021-04-07 06:00:30"
            "created_at" => "2021-04-07 06:00:30"
          ]
        }

    ERRORS:

        Status: 404 Not Found 


        ## ROLES            ## ROLES            
          <strong>Page:</strong> ROLES            ## ROLES                
<strong>Method:</strong> GET
<strong>Name:</strong> GET ROLES
<strong>Description:</strong> GET ROLES
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/role 

<strong>Request:</strong>

    Headers:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"  
    

<strong>Responses:</strong>
    SUCCESS:
        Status: 200 Ok
    
        Example:
        {
          "data": {
            [
              "id" => 1
              "group" => "Steve Rempel"
              "slug" => "et-pariatur-quo-ex-rerum-fugiat-pariatur-adipisci"
              "name" => "Dr. Owen Gaylord"
              "updated_at" => "2021-04-07 06:03:04"
              "created_at" => "2021-04-07 06:03:04"
            ]
          },
          {
            [
              "id" => 2
            "group" => "Josianne Haley"
            "slug" => "nostrum-aliquid-mollitia-eum-vel-ea-velit-ipsam"
            "name" => "Pauline Schroeder"
            "updated_at" => "2021-04-07 06:00:30"
            "created_at" => "2021-04-07 06:00:30"
            ]
          }
        }

    ERRORS:
        Status: 404 Not Found

## ROLES            
  <strong>Page:</strong> ROLES                
<strong>Method:</strong> PATCH
<strong>Name:</strong> UPDATE ROLE
<strong>Description:</strong> UPDATE ROLE
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/role/{{id}}

<strong>Request:</strong>

    Headers:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"  
    
    Parameters:
    "group": "Josianne Haley", (type: string, required: true, description: Group of role )
    "slug": "nostrum-aliquid-mollitia-eum-vel-ea-velit-ipsam", (type: string, required: true, description: Slug for role )
    "name": "Pauline Schroeder", (type: string, required: true, description: Name of role )
    
<strong>Responses:</strong>
    SUCCESS:
        Status: 204 Ok

    ERRORS:
        Status: 404 Not Found 

## ROLES            
  <strong>Page:</strong> ROLES                
<strong>Method:</strong> GET
<strong>Name:</strong> SHOW ROLE
<strong>Description:</strong> SHOW ROLE
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/role/{{id}}

<strong>Request:</strong>

    Headers:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"  
    
    Parameters:
    "id": 1, (type: string, required: true, description: Id of role )
    
<strong>Responses:</strong>
    SUCCESS:
        Status: 204 Ok

        Example:
        {
          "data": [
            "id" => 1
            "group" => "Josianne Haley"
            "slug" => "nostrum-aliquid-mollitia-eum-vel-ea-velit-ipsam"
            "name" => "Pauline Schroeder"
            "updated_at" => "2021-04-07 06:00:30"
            "created_at" => "2021-04-07 06:00:30"
          ]
        }

    ERRORS:
        Status: 404 Not Found 

## PERMISSION            
  <strong>Page:</strong> PERMISSION               
<strong>Method:</strong> POST   
<strong>Name:</strong> New PERMISSION   
<strong>Description:</strong> ADD New PERMISSION    
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/permission     

<strong>Request:</strong>

    Headers:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"

    Parameters:
    "group": "Josianne Haley", (type: string, required: true, description: Group of permission )
    "slug": "nostrum-aliquid-mollitia-eum-vel-ea-velit-ipsam", (type: string, required: true, description: Slug for permission )
    "name": "Pauline Schroeder", (type: string, required: true, description: Name of permission )


<strong>Responses:</strong>
    SUCCESS:
        Status: 200 Ok

        Example:
        {
          "data": [
            "id" => 1
            "group" => "Josianne Haley"
            "slug" => "nostrum-aliquid-mollitia-eum-vel-ea-velit-ipsam"
            "name" => "Pauline Schroeder"
            "updated_at" => "2021-04-07 06:00:30"
            "created_at" => "2021-04-07 06:00:30"
          ]
        }

    ERRORS:

        Status: 404 Not Found 

## PERMISSION
  <strong>Page:</strong> PERMISSION   
        ## PERMISSION        ## PERMISSION
          <strong>Page:</strong> PERMISSION        ## PERMISSION    
<strong>Method:</strong> GET
<strong>Name:</strong> GET PERMISSIONS
<strong>Description:</strong> GET PERMISSIONS
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/permission 

<strong>Request:</strong>

    Headers:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"  
    

<strong>Responses:</strong>
    SUCCESS:
        Status: 200 Ok
    
        Example:
        {
          "data": {
            [
              "id" => 1
              "group" => "Steve Rempel"
              "slug" => "et-pariatur-quo-ex-rerum-fugiat-pariatur-adipisci"
              "name" => "Dr. Owen Gaylord"
              "updated_at" => "2021-04-07 06:03:04"
              "created_at" => "2021-04-07 06:03:04"
            ]
          },
          {
            [
              "id" => 2
            "group" => "Josianne Haley"
            "slug" => "nostrum-aliquid-mollitia-eum-vel-ea-velit-ipsam"
            "name" => "Pauline Schroeder"
            "updated_at" => "2021-04-07 06:00:30"
            "created_at" => "2021-04-07 06:00:30"
            ]
          }
        }

    ERRORS:
        Status: 404 Not Found 

## PERMISSION
  <strong>Page:</strong> PERMISSION   
<strong>Method:</strong> PATCH
<strong>Name:</strong> UPDATE PERMISSION
<strong>Description:</strong> UPDATE PERMISSION
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/permission/{{id}}

<strong>Request:</strong>

    Headers:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"  
    
    Parameters:
    "group": "Josianne Haley", (type: string, required: true, description: Group of permission )
    "slug": "nostrum-aliquid-mollitia-eum-vel-ea-velit-ipsam", (type: string, required: true, description: Slug for permission )
    "name": "Pauline Schroeder", (type: string, required: true, description: Name of permission )
    
<strong>Responses:</strong>
    SUCCESS:
        Status: 204 Ok

    ERRORS:
        Status: 404 Not Found 

## PERMISSION        
  <strong>Page:</strong> PERMISSION           
<strong>Method:</strong> GET
<strong>Name:</strong> SHOW PERMISSION
<strong>Description:</strong> SHOW PERMISSION
<strong>Endpoint:</strong> http://{{subdomain}}.{{domain}}/permission/{{id}}

<strong>Request:</strong>

    Headers:  
    "X-XSRF-TOKEN" : "eyJpdiI6IjhmR...", (type: string, required: true, description: Obtain from GET request to "http://{{domain}}/sanctum/csrf-cookie"  
    
    Parameters:
    "id": 1, (type: string, required: true, description: Id of permission )
    
<strong>Responses:</strong>
    SUCCESS:
        Status: 204 Ok

        Example:
        {
          "data": [
            "id" => 1
            "group" => "Josianne Haley"
            "slug" => "nostrum-aliquid-mollitia-eum-vel-ea-velit-ipsam"
            "name" => "Pauline Schroeder"
            "updated_at" => "2021-04-07 06:00:30"
            "created_at" => "2021-04-07 06:00:30"
          ]
        }

    ERRORS:
        Status: 404 Not Found 