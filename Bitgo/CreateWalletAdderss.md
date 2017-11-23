**Create Wallet Address**
----
Description:create a new receive address for your wallet.

* **URL:**

    /bitgo/generateWalletAddress

* **Method:**

   POST

   
 * **Query String Parameters:**<br />
   
* **Headers:**

Content-Type: "application/json"

Authorization(bitgo access-token)        {String} *Required. 
   
* **Query Parameters:**
<pre>
{
   coin   {String} *Required coin.
   id   {String} *Required Id of the wallet.
}
</pre>

* **Body Parameters:**

gasPrice   {Integer} Optional gasPrice.
	   
* **Example:**

	{
		"gasPrice":100,
		"id":"5a15790fb1d959c307149a60a7bc5a98"
	}

* **Success Response:**

* **Code:** 200 <br />
  
* **Content:**
<pre>
{
    "data": {
        "id": "5a16b21102dd91c107f99963c9863ee3",
        "address": "QijmP4XDfEKzcf9DLRnQZ1XSP3eQG5gCf7",
        "chain": 0,
        "index": 1,
        "coin": "tltc",
        "wallet": "5a15790fb1d959c307149a60a7bc5a98",
        "coinSpecific": {
            "redeemScript": "5221035d9dfcada1118a90445b095c190d2d8212358604f398f2fa2c01c80640b6df942102eb604fb03216006643fd9c36fb110beeb3f3c585c337518f928b169a4522c6592103d35cb4cf877edc58a5d554710b1b73adf1fdda6451ff464f3927b2ff048cfeaf53ae"
        }
    },
    "meta": {
        "version": "1.0",
        "received": "2017-11-23T11:34:20.043Z",
        "executed": 1511436864750
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
	"meta": 
	{
	  "version": "1.0",
	  "received": "2017-11-23T11:35:40.906Z",
	  "executed": 1511436940906
	},
	"response": 
	{ 
	  "code": 401,
	  "errors": 
	  [
	    {
		    "param": "id",
		    "msg": "wallet id is required",
		    "value": ""
		}
	   ],
	"message": "Error"
			
	}
}
</pre>