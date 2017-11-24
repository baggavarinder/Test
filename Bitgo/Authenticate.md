**Bitgo Authenticate Api**
----
Description : authenticate the user.

* **URL**

    bitgo/authenticate

* **Method:** 

    POST
  

* **Data Params** <br />

<pre>
{
	 username   {String} *Required User's email address.
	 password   {String} *Required password.
	 otp        {String} *Required 2nd factor authentication token.
}	 
</pre>   

* **Example:** <br/>

<pre>
{ 
  "username": "baggavarinder@gmail.com",
  "password": "sol!mp2^5sp",
  "otp":      "248989" 
}
</pre>  

* **Success Response:**

	Code: 200 
 
<pre>
{
    "data": {
        "token_type": "bearer",
        "expires_in": 3600,
        "expires_at": 1511437931,
        "scope": [
            "user_manage",
            "openid",
            "profile",
            "wallet_create",
            "wallet_freeze_all",
            "wallet_manage_all",
            "wallet_approve_all",
            "wallet_spend_all",
            "wallet_edit_all",
            "wallet_view_all"
        ],
        "user": {
            "id": "5a12d741e81077b9079558efc7d0068b",
            "username": "baggavarinder@gmail.com",
            "name": {
                "full": "baggavarinder@gmail.com"
            },
            "email": {
                "email": "baggavarinder@gmail.com",
                "verified": true
            },
            "phone": {
                "phone": "",
                "verified": false
            },
            "identity": {
                "verified": false
            },
            "otpDevices": [
                {
                    "id": "5a12d789e81077b907955d81d339e309",
                    "type": "totp",
                    "label": "Google Authenticator",
                    "verified": true
                }
            ],
            "disableReset2FA": false,
            "currency": {
                "currency": "USD",
                "bitcoinUnit": "BTC"
            },
            "timezone": "US/Pacific",
            "isActive": true,
            "ecdhKeychain": "xpub661MyMwAqRbcEzxiDu2gG3DB4wrwvFpM6DWTAn5wAW9XoN3rVrMxW3PELqhK5dzfWjP76MxHmxf9g2GTtfWquP8RUndodwCUyHAUsFWbs3y",
            "referrer": {},
            "apps": {
                "coinbase": {}
            },
            "forceResetPassword": false,
            "allowedCoins": [],
            "agreements": {
                "termsOfUse": 1,
                "termsOfUseAcceptanceDate": "2017-11-20T13:24:28.485Z"
            }
        },
        "encryptedToken": "{\"iv\":\"pQu8ULrcKcCLUwpT7226AA==\",\"v\":1,\"iter\":1000,\"ks\":128,\"ts\":64,\"mode\":\"ccm\",\"adata\":\"\",\"cipher\":\"aes\",\"salt\":\"AaZFRaxUiJA=\",\"ct\":\"aZl+1cFeDlEWXqe6rriIbGjWYUdZi7MRXYZcdwXRM2m9i4cUsyI/wIQhGo08nXFAA40i7F/O/YBPrkfZN+EfIMgOESe9bG/a4UII\"}",
        "derivationPath": "m/999999/60446403/218411772",
        "encryptedECDHXprv": "{\"iv\":\"VmsDgepJALQUvQZMKt94NA==\",\"v\":1,\"iter\":10000,\"ks\":256,\"ts\":64,\"mode\":\"ccm\",\"adata\":\"\",\"cipher\":\"aes\",\"salt\":\"EQvGFVfeuA0=\",\"ct\":\"wtBIziqaJkxd7LjhGe0rXxn4lmWxbSK1LHdjKrBLpRedSENMVl7Fzrw9IWKQWDWuYJpoikqjBO2E5QKa0YlqX4v9RH0caGT1aIxtFLkJdAiVB9+PrmEnGoAo6PizMM46eqOgQrxiZUJ/r8Pz6Zu2w+La/a7l2PA=\"}",
        "access_token": "v2xa6b1a63302b37561a7cc370cb10d886223e574aa69cc98f08b693d3b649360af"
    },
    "meta": {
        "version": "1.0",
        "received": "2017-11-23T10:52:56.298Z",
        "executed": 1511434379369
    },
    "response": {
        "code": 200,
        "errors": {},
        "message": "OK"
    }
}
</pre>
	
* **Error Response:**

	Code: 401 NOT FOUND

<pre>
{
  "data": {},
  "meta": 
    {
      "version": "1.0",
      "received": "2017-11-23T10:49:11.104Z",
      "executed": 1511434153310
    },
	"response": 
	{
	 "code": 400,
	 "errors": 
	  {
	    "status": 401,
	    "result": 
	    {
		  "name": "OAuth2Error",
		  "message": false,
		  "needsOTP": true,
		  "needsAuthy": true,
		  "code": 401,
		  "error": "needs_otp",
		  "error_description": "needs_otp"
	    },
	 "needsOTP": true
	},
   "message": "Error"
}
</pre>

OR

<pre>
{
  "data": {},
  "meta": 
   {
     "version": "1.0",
     "received": "2017-11-23T10:49:11.104Z",
     "executed": 1511434153310
   },
  "response": 
    {
      "code": 400,
	  "errors": 
	  [
       {
         "param": "username",
         "msg": "id is required",
         "value": ""
        },
        {
         "param": "password",
          "msg": "wallet type is required",
         "value": ""
        },
        {
          "param": "otp",
          "msg": "2fa token is required",
          "value": ""
        }
    ],
   "message": "Error"
  }
}
</pre>
