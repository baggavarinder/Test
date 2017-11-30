**User Register Api**
----
Description : User Register Api.

* **URL**

    /signup

* **Method:** 

    POST
  

* **Data Params** <br />

<pre>
{
	email   {String} *Required User's email address.
	phone  string *Required.
	phoneCode        {String} *Required.
	password {String} *Required password.
    confirmPassword {String} *Required password.
}	 
</pre>   

* **Example:** <br/>

<pre>
{
	"email":"test@gmail.com",
	"phone":"4564564564",
	"phoneCode":"91",
	"password":"1234",
	"confirmPassword":"1234"
}
</pre>  

* **Success Response:**

	Code: 200 
	
* **Content:**<br />
 
<pre>
{
    "data": {
        "success": true,
        "message": "User created, please verify user"
    },
    "meta": {
        "version": "1.0",
        "received": 1512028052563,
        "executed": 1512028054393
    },
    "response": {
        "code": 200,
        "errors": {},
        "message": "OK"
    }
}
</pre>
	
* **Error Response:**

	Code: 400 NOT FOUND

* **Content:**<br />
	
<pre>
{
    "data": {},
    "meta": {
        "version": "1.0",
        "received": 1512029164743,
        "executed": 1512029164745
    },
    "response": {
        "code": 400,
        "errors": [
            {
                "param": "email",
                "msg": "Email is not valid"
            },
            {
                "param": "phone",
                "msg": "Phone is required"
            },
            {
                "param": "phoneCode",
                "msg": "Phone Code is required"
            },
            {
                "param": "password",
                "msg": "Password must be at least 4 characters long"
            },
            {
                "param": "confirmPassword",
                "msg": "Passwords do not match"
            }
        ],
        "message": "Error"
    }
}
</pre>

OR

<pre>
{
    "data": {},
    "meta": {
        "version": "1.0",
        "received": 1512029218684,
        "executed": 1512029218696
    },
    "response": {
        "code": 400,
        "errors": [
            {
                "param": "password",
                "msg": "Password must be at least 4 characters long",
                "value": "124"
            }
        ],
        "message": "Error"
    }
}
</pre>
