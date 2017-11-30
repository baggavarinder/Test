**User login Api**
----
Description : User login Api.

* **URL**

    /login

* **Method:** 

    POST
  

* **Data Params** <br />

<pre>
{
	email   {String} *Required User's email address.
	password {String} *Required password.
}	 
</pre>   

* **Example:** <br/>

<pre>
{
	{
	"email":"test@gmail.com",
	"password":"1234"
}
}
</pre>  

* **Success Response:**

	Code: 200 
	
* **Content:**<br />
 
<pre>
{
    "data": {
        "message": "auth code is sent on your mobile",
        "sucess": true
    },
    "meta": {
        "version": "1.0",
        "received": 1512028056433,
        "executed": 1512028058495
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
        "received": 1512029537598,
        "executed": 1512029537598
    },
    "response": {
        "code": 400,
        "errors": [
            {
                "param": "email",
                "msg": "Email is not valid",
                "value": ""
            },
            {
                "param": "password",
                "msg": "Password cannot be blank",
                "value": ""
            }
        ],
        "message": "Error"
    }
}
</pre>

