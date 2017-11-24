**Generate Wallet Api**
----
Description : generate wallet.

* **URL:**

	bitgo/createWallet

* **Method:**

	POST
   
* **Query String Parameters:**<br />
   
* **Headers:**

	Content-Type: "application/json"

	Authorization {String} *Required : "bitgo access-token"
   	  
* **Body:**
<pre>
{
    label        {String} *Required name for the wallet
	passphrase   {String} *Required Passphrase to decrypt the wallet’s private key
	wallettype   {String} *Required wallet type of coin.
}    
</pre>

* **Example:**
<pre>
	{
		"label":"leela",
		"passphrase":"secretpassphrase1a5df8380e0e30",
		"walletType":"tltc"
	}
</pre>

* **Success Response:**

	Code: 200 <br />

* **Content:**
<pre>
{
    "data": {
        "wallet": {
            "bitgo": {
                "user": null,
                "token": "v2x3585a41dc7b3dd8223b53253cfbc7a7bc42856636385dd678ba7b7c713f79a8f",
                "extensionKey": null
            },
            "_wallet": {
                "id": "5a16a474009c68b707870f15f36aafce",
                "users": [
                    {
                        "user": "5a12d741e81077b9079558efc7d0068b",
                        "permissions": [
                            "admin",
                            "view",
                            "spend"
                        ]
                    }
                ],
                "coin": "tltc",
                "label": "leela",
                "m": 2,
                "n": 3,
                "keys": [
                    "5a16a471cc47dbba079a031dc1433329",
                    "5a16a471009c68b707870efaafd2f823",
                    "5a16a47102dd91c107f913474287a1cb"
                ],
                "tags": [
                    "5a16a474009c68b707870f15f36aafce"
                ],
                "disableTransactionNotifications": false,
                "freeze": {},
                "deleted": false,
                "approvalsRequired": 1,
                "isCold": false,
                "coinSpecific": {},
                "admin": {},
                "clientFlags": [],
                "balance": 0,
                "confirmedBalance": 0,
                "spendableBalance": 0,
                "balanceString": "0",
                "confirmedBalanceString": "0",
                "spendableBalanceString": "0",
                "receiveAddress": {
                    "id": "5a16a474009c68b707870f19f039211e",
                    "address": "QPxav3fqXvkBfxDQQfajcyr7vsovZnKp7F",
                    "chain": 0,
                    "index": 0,
                    "coin": "tltc",
                    "wallet": "5a16a474009c68b707870f15f36aafce",
                    "coinSpecific": {
                        "redeemScript": "522102fb52ede2d173c5079e2272957d95145d6739b212a773e60b4096c97df461bbe62103805239f4901553d4ae564033663e667eac4c8c4a278d64521b919101a9dcadf22102cb79fddaf1777ecc86a1a105f608ba432f06e2c3642584b0b1fcb77c0d38984553ae"
                    }
                },
                "pendingApprovals": []
            }
        },
        "userKeychain": {
            "id": "5a16a471cc47dbba079a031dc1433329",
            "users": [
                "5a12d741e81077b9079558efc7d0068b"
            ],
            "pub": "xpub661MyMwAqRbcGXuRAVk1tZXCLhubKBrrMF9898ykfAn7jCHiHFtVLRMA2hJ8KUFzovLHyRbyfo6etmpyZ5xFJCeu1pK3BvbLdQTYj59aA5Q",
            "ethAddress": "0xbdf3f53f8ac238b011fd10b8cab338734829a81e",
            "encryptedPrv": "{\"iv\":\"/b4qig/Z+FyZCwAvM4Umqg==\",\"v\":1,\"iter\":10000,\"ks\":256,\"ts\":64,\"mode\":\"ccm\",\"adata\":\"\",\"cipher\":\"aes\",\"salt\":\"1ussLRrW1vc=\",\"ct\":\"fvuF7tcET4jPOXdQQ19vYWDznORHeWEJIFniICxjKXRQoz3dWNmNA0aIaOUcXNXFyJrDpu21PA7WBYJudLzPKBZl5dr2smHhaUZMScmThzzXohm3CM0bUnmple4AZkbWGJ1jjynJ/dJU8/VbTYjflQ8ovfKPCuU=\"}",
            "prv": "xprv9s21ZrQH143K43px4UD1XRaTng56uj8zz2DXLka96qF8rPxZjiaEnd2gBQcDcCHp79pScfH4qBC66YbEeV2MUKJqUNkT6Gt1Mwx15tsfkty"
        },
        "backupKeychain": {
            "id": "5a16a471009c68b707870efaafd2f823",
            "users": [
                "5a12d741e81077b9079558efc7d0068b"
            ],
            "pub": "xpub661MyMwAqRbcEzM4WghhP3Ch5t3LAzzCnggc7EvWEdNUXXS2gFKWYjCjuff4rMpfYRJqY3q4qQeUVABpbgfvgFg1h8BAueLyBvQ8gGUiD7C",
            "ethAddress": "0x9407a44a59c9f29a5357bc89a74a6f01a2f1a81a",
            "prv": "xprv9s21ZrQH143K2WGbQfAh1uFxXrCqmYGMRTm1JrWtgHqVej6t8i1FzvtG4P9awhbGqirKoFcNvMhGVYXjgrXtebqYgDuFDbsWP6pbypG9vSp",
            "source": "backup"
        },
        "bitgoKeychain": {
            "id": "5a16a47102dd91c107f913474287a1cb",
            "users": [
                "5a12d741e81077b9079558efc7d0068b"
            ],
            "pub": "xpub661MyMwAqRbcGo1ER96smeiAnta6ae1UCCd5D6KoLoxrHyusy1BVuyHUUAYY8aDnJ8sC62ukooDa1HsfDC8CuFapiEfhVfhGV1ejptJ6PEz",
            "ethAddress": "0x2f74ecf2338d45cde33cc5f8875c82a3fd3c0c0e",
            "isBitGo": true
        },
        "warning": "Be sure to backup the backup keychain -- it is not stored anywhere else!"
    },
    "meta": {
        "version": "1.0",
        "received": "2017-11-23T10:36:14.412Z",
        "executed": 1511433379848
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
  
* **Content:** 
<pre>
{
	"data": {},
	"meta": 
	{
		"version": "1.0",
		"received": "2017-11-23T11:03:20.235Z",
		"executed": 1511435000235
	},
	"response": 
	{
		"code": 401,
		"errors":
		[{
			"param": "passphrase",
			"msg": "passphrase is required",
			"value": ""
		}],
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