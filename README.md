**Authentication API**
----
  Returns json data about logged in user.

* **URL**

  /authentication/tokens

* **Method:**

  `Post`
  

* **Data Params** <br />
<pre>
{
	Login: string, //Required
	Password: string //Required
}
</pre>
* **Headers:**

  Content-Type: "application/x-www-form-urlencoded"

* **Success Response:**

  * **Code:** 200 <br />

* **Content:** 
<pre>
{
    "data": {
        "token": "xyzz",
        "lifetime": 2141364768
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

  * **Code:** 401 NOT FOUND <br />
  
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
        "errors": {
            "message": "Login name test@gmail.com not found."
        },
        "message": "Error"
    }
}
</pre>
OR
 * **Code:** 401 UnAuthorized <br />

* **Content:** 
 <pre>{
    "data": {},
    "meta": {
        "version": "1.0",
        "received": 1510646586222,
        "executed": 1510646586222
    },
    "response": {
        "code": 401,
        "errors": [
            {
                "param": "password",
                "msg": "Password is required",
                "value": ""
            }
        ],
        "message": "Error"
    }
}
</pre>
**Revoke authentication token (sign out)**
----
  Returns json data.

* **URL**

  /authentication/tokens

* **Method:**

  `Put`
  

* **Data Params** </br>
<pre>
{
	token: [string] // Required
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
        "message": "success"
    },
    "meta": {
        "version": "1.0",
		"received": 1510645738705,
        "executed": 1510645517769
    },
    "response": {
        "code": 200,
        "errors": {},
        "message": "OK"
    }
}
</pre>
* **Error Response:**

  * **Code:** 401 Token not found <br />
  
* **Content:** 
<pre>
{
    "data": {},
    "meta": {
        "version": "1.0",
		"received": 1510645738705,
        "executed": 1510645554641
    },
    "response": {
        "code": 401,
        "errors": {
            "message": "No Token found."
        },
        "message": "Error"
    }
}
</pre>
OR
  * **Code:** 401 UnAuthorized <br />
  
* **Content:** 
<pre>
{
    "data": {},
    "meta": {
        "version": "1.0",
        "received": 1510646686334,
        "executed": 1510646686334
    },
    "response": {
        "code": 401,
        "errors": [
            {
                "param": "token",
                "msg": "Token is required",
                "value": ""
            }
        ],
        "message": "Error"
    }
}
</pre> 
**Send Reset Password Link API**
----
  Returns json data.

* **URL**

  /sso/tokens

* **Method:**

  `Post`
  

* **Data Params** </br>
<pre>
{
	"email":[string] //Required
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
        "message": "An e-mail has been sent to test@gmail.com with further instructions.",
        "resetToken": "9ebb8ebcf7a741d9b9b9884e306a35f9",
        "tokenExpiryTime": "2017-11-14T08:55:45.124Z"
    },
    "meta": {
        "version": "1.0",
        "received": 1510646145113,
        "executed": 1510646149087
    },
    "response": {
        "code": 200,
        "errors": {},
        "message": "OK"
    }
}
</pre> 
* **Error Response:**

  * **Code:** 500 Internal Server Error <br />
  
* **Content:** 
<pre>
{
    "data": {},
    "meta": {
        "version": "1.0",
        "received": 1510646187676,
        "executed": 1510646187678
    },
    "response": {
        "code": 500,
        "errors": {
            "message": "Invalid Email address."
        },
        "message": "Error"
    }
}
</pre>
OR
  * **Code:** 401 UnAuthorized <br />
  
* **Content:** 
<pre>
{
    "data": {},
    "meta": {
        "version": "1.0",
        "received": 1510646243157,
        "executed": 1510646243157
    },
    "response": {
        "code": 401,
        "errors": [
            {
                "param": "email",
                "msg": "Email is required",
                "value": ""
            }
        ],
        "message": "Error"
    }
}
</pre>
**Reset Password API**
----
  Returns json data about a updated password.

* **URL**

  /users/:userId/passwords/:token

* **Method:**

  `Put`
  

* **Data Params** </br>
<pre>
{
	"password":"1234", //Reqruied
	"confirmPassword":"1234" //Required
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
        "message": "Password has been updated successfully."
    },
    "meta": {
        "version": "1.0",
        "received": 1510646326192,
        "executed": 1510646326375
    },
    "response": {
        "code": 200,
        "errors": {},
        "message": "OK"
    }
}
</pre> 
* **Error Response:**

  * **Code:** 500 Internal Server Error <br />
  
* **Content:** 
<pre>
{
    "data": {},
    "meta": {
        "version": "1.0",
        "received": 1510646441853,
        "executed": 1510646441854
    },
    "response": {
        "code": 500,
        "errors": {
            "message": "Password reset token is invalid or has expired."
        },
        "message": "Error"
    }
}
</pre>
OR
  * **Code:** 401 UnAuthorized <br />
  
* **Content:** 
<pre>
{
    "data": {},
    "meta": {
        "version": "1.0",
        "received": 1510646510000,
        "executed": 1510646510000
    },
    "response": {
        "code": 401,
        "errors": [
            {
                "param": "password",
                "msg": "Password must be at least 4 characters long.",
                "value": ""
            },
            {
                "param": "password",
                "msg": "Password must be at least 4 characters long.",
                "value": ""
            }
        ],
        "message": "Error"
    }
}
</pre>