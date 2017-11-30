**User Verify Auth  Api**
----
Description : User login Api.

* **URL**

    /verify

* **Method:** 

    POST
  

* **Data Params** <br />

<pre>
{
	code   {String} *Required User's email address.
}	 
</pre>   

* **Example:** <br/>

<pre>
{
	{
	"code":"0000",

}
}
</pre>  

* **Success Response:**

	Code: 200 
	
* **Content:**<br />
 
<pre>
{
    "data": {
        "message": "verify"
    },
    "meta": {
        "version": "1.0",
        "received": 1512029952110,
        "executed": 1512029953583
    },
    "response": {
        "code": 200,
        "errors": {},
        "message": "OK"
  
</pre>
	
* **Error Response:**

	Code: 500 NOT FOUND

* **Content:**<br />
<pre>
{
    "data": {},
    "meta": {
        "version": "1.0",
        "received": 1512029740279,
        "executed": 1512029740702
    },
    "response": {
        "code": 500,
        "errors": {
            "message": "No pending verifications for +91 987-285-1423 found.",
            "success": false,
            "errors": {
                "message": "No pending verifications for +91 987-285-1423 found."
            },
            "error_code": "60023"
        },
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
        "received": 1512029933776,
        "executed": 1512029933777
    },
    "response": {
        "code": 400,
        "errors": [
            {
                "param": "code",
                "msg": "Code must be 4 characters long",
                "value": "123"
            }
        ],
        "message": "Error"
    }
}
</pre>


