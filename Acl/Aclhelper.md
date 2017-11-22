**Acl Helper Allow Permission API**
----
allow( roles, resources, permissions, function(err) )

Adds the given permissions to the given roles over the given resources. These permission are defined in server.ts file only.


* **Data Params** <br />
<pre>
    roles       {String|Array} role(s) to add permissions to. (Required)
    resources   {String|Array} resource(s) to add permisisons to. (Required)
    permissions {String|Array} permission(s) to add to the roles over the resources. (Required)
</pre>  
* **Sample data for adding permission** <br />
<pre>
[
	{
		 "roles": ["guest", "admin"] , 
		 "allows":[ { "resources": "url to add the permission", "permissions": ["methodType","methodType"] } ] 
    }
]
	
</pre>


**Acl Assign Role API**
----
allow( roles, resources, permissions, function(err) )

Adds roles to a given user id.

* **URL**

  /assignUserRole

* **Method:**

  `Post`
  

* **Data Params** <br />
<pre>
    userId   {String|Number} User id. (Required)
    roles    {String|Array} Role(s) to add to the user id.(Required)
</pre>
* **Exapmle** <br />
<pre>

{
  "userId":"test",
  "role":"rolename"
}
	
</pre>
* **Headers:**

  Content-Type: "application/json"

* **Success Response:**

  * **Code:** 200 <br />

* **Content:** 
<pre>
{
     "data": {
        "response": {
            "Message": "Role added"
        }
    },
    "meta": {
        "version": "1.0",
		"received": 1510645738705,
        "executed": 1510644768421
    },
    "response": {
        "code": 200,
        "errors": {},
        "message": "OK"
    }
}

</pre> 
* **Error Response:**

  * **Code:** 400 NOT FOUND <br />
  
* **Content:** 
<pre>
 {
    "data": {},
    "meta": {
        "version": "1.0",
		"received": 1510645738705,
        "executed": 1510644863715
    },
    "response": {
        "code": 401,
        "errors": [
            {
                "param": "user",
                "msg": "user is required",
                "value": ""
            },
            {
                "param": "role",
                "msg": "role is required",
                "value": ""
            }
        ],
        "message": "Error"
    }
}
</pre>

**Acl Get Role API**
----
allow( roles, resources, permissions, function(err) )

Adds roles to a given user id.

* **URL**

  /getPermission

* **Method:**

  `Post`
  

* **Data Params** <br />
<pre>
   userId    {String|Number} User id.
    resources {String|Array} resource(s) to ask permissions for.
</pre>
* **Exapmle** <br />
<pre>
{
"userId":"test",
"resource":"resource(s) to ask permissions for"
}
	
</pre>
* **Headers:**

  Content-Type: "application/json"

* **Success Response:**

  * **Code:** 200 <br />

* **Content:** 
<pre>
{
     "data": {
        "response": {
            "Message": "Role added"
        }
    },
    "meta": {
        "version": "1.0",
		"received": 1510645738705,
        "executed": 1510644768421
    },
    "response": {
        "code": 200,
        "errors": {},
        "message": "OK"
    }
}

</pre> 
* **Error Response:**

  * **Code:** 400 NOT FOUND <br />
  
* **Content:** 
<pre>
 {
    "data": {},
    "meta": {
        "version": "1.0",
		"received": 1510645738705,
        "executed": 1510644863715
    },
    "response": {
        "code": 401,
        "errors": [
            {
                "param": "user",
                "msg": "user is required",
                "value": ""
            },
            {
                "param": "resource",
                "msg": "resource is required",
                "value": ""
            }
        ],
        "message": "Error"
    }
}
</pre>