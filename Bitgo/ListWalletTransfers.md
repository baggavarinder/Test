**List wallet transfers**
----
Description : Retrieves a list of transfers.

* **URL:**

    /bitgo/getWalletTransactions

* **Method:**

    GET

   
* **Query String Parameters:**<br />
<pre>
{
   coin   {String} *Required coin.
   id     {String} *Required Id of the wallet.
}
</pre> 

* **Headers:**

   Content-Type: "application/json"

   Authorization {String} *Required : "bitgo access-token"

* **Success Response:**<br />

    Code: 200 
  
* **Content:**<br />

<pre>
{
		
    "data": {
        "coin": "tltc",
        "transfers": []
    },
    "meta": {
        "version": "1.0",
        "received": "2017-11-23T11:43:38.326Z",
        "executed": 1511437422515
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
        "received": "2017-11-23T11:44:13.410Z",
        "executed": 1511437453410
    },
    "response": {
        "code": 401,
        "errors": [
            {
                "param": "coin",
                "msg": "walllet type is required",
                "value": ""
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
        "received": "2017-11-23T13:03:15.415Z",
        "executed": 1511442197517
    },
    "response": {
        "code": 401,
        "errors": {
            "status": 401,
            "result": {
                "error": "unauthorized",
                "name": "Unauthorized",
                "requestId": "cjachmred5crciyrs18kbtum7"
            },
            "invalidToken": true
        },
        "message": "Error"
    }
}
</pre>
