**Mandrill Email Sent  API**
----
Send a new transactional message through Mandrill

* **URL**

  /emailSent

* **Method:**

  `Post`
  

* **Data Params** <br />
<pre>
{
	template_name   :{String} Required* name of a template. 
	
	template_content:{Array} Required* array of template content. 
	Each item of array contain two keys:ame(name of the content block) and title(actual title to put). 
						 
	message(Required*)         
	{
		 to:{Array} Required* Parameters: 
		[{
			Email:{string} Required* email address of the recipient.
			Name :{string} Optional  display name.
			Type :{string} Optional  If not provide default is "to" .
		}]
		
	from_email:{string}  Required* sender email address.
	html      :{string}  optional full HTML
	subject   :{string}  optional message subject
	from_name :{string}  optional from name
	text      :{string}  optional full text
	
	} 
	
	send_at:{string}  Optional  for scheduling email at a specific time. Validation: datetime 
	ip_pool:{string}  Optional  name of the dedicated ip pool to be used 
	async  :{boolean} Optional  Default to false for less than 10 recipient and true for more than 10 recipient. 
}
</pre>
* **Exapmle** <br />
<pre>
{
  "template_name": "test13452",
  "template_content":
  [{
	"name": "test", 
	 "title": "Mandrill Testing" 
}],
   "message":
    { 
	"to":
	[
	   {
		 "name": "test",
		 "email": "test@test.com", 
		 "type": "to"
	   }, 
	   {
		  "name": "test1", 
		  "email": "test@test.com",
		  "type": "to"
	   }
	],
	"from_email": "test@test.com",
	"html": "Test",
	"subject": "Test",
	"from_name": "Test",
	"text": "Testing mandrill" 	
    },
  "send_at": "2017-11-22T08:19:31.299Z",
  "ip_pool": "Main-pool",
  "async": "false"
}
</pre>
* **Headers:**

  Content-Type: "application/json"

* **Success Response:**

  * **Code:** 200 <br />

* **Content:** 
<pre>
{
     "data": [
        {
            "email": "test@test.com",
            "status": "queued",
            "_id": "59d3f80fe3f44bfdba92e29ef107e7cd"
        },
        {
            "email": "test1@test.com",
            "status": "queued",
            "_id": "8d4d376116eb4c2fb25cf67fb7989950"
        }
    ],
    "meta": 
	{
	   "version": "1.0",
	   "received": 1510645738705,
	   "executed": 1510644768421
    },
    "response": 
	{
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
    "meta":
	{
	  "version": "1.0",
	  "received": 1510645738705,
	  "executed": 1510644863715
    },
    "response": {
        "code": 400,
         "errors": {
            "status": "error",
            "code": 5,
            "name": "Unknown_Template",
            "message": "No such template \"test13452\""
        },
        "message": "Error"
    }
}
</pre>