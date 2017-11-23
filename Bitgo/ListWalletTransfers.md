* **List wallet transfers**

   * **Description:**
   Retrieves a list of transfers.

   * **URL:**
   /bitgo/getWalletTransactions

   * **Method: **
   GET

   
   * **Query String Parameters:**<br />
   
   * **Headers:**

		Content-Type: "application/json"
   
		Authorization(bitgo access-token)        {String} *Required 
   
   
    * **Query Parameters:**
						  coin   {String} *Required coin.
							id   {String} *Required Id of the wallet.
			
	
							
    
    * **Example:**

	{
		"coin":"tltc",
		"id":"5a15790fb1d959c307149a60a7bc5a98"
	}

		* **Success Response:**

		* **Code:** 200 <br />
  
		* **Content:**

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
		
		
		* **Error Response:**

		* **Code:** 401 NOT FOUND <br />
  
		* **Content:** 
		
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