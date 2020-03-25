# Welcome to NBDomain!

[NBDomain](https://nbdomain.com/) is a decentralised domain system based on BitCoin SV technology. Users are able to use NBDomain to access blockchain resources with [Maxthon 6 browser](https://www.maxthon.com/).

Developers can use NBDomain NodeJS client SDK to register, renew, transfer nbdomain, and save data into nbdomain. All operations will eventually convert into transactions on blockchain.


# HTTP API
Developers can use NBDomain data service to get domain information.

    curl https://manage.nbdomain.com/node/?nid=example.test

The response of  HTTP API looks like the following:

    {
       "code":0,  // (int) Response code of the request.
       "message":"SUCCEED",  // (string) Response message.
       "obj":{
          "nid":"example.test",  // (string) A nbdomain.
          "owner_key":<Public key>,  // (string) Public key of the domain owner.
          "owner":<Address>,  // (string) Address of domain owner.
          "status":<Status>,  // (int) Status of the domain. 0=expired, 1=valid.
          "lasttxts":<Timestamp>,  // (int) Timestamp of last transaction time.
          "keys": {  // (Object) List of key, value pairs in domain space.
	          subdomain1: value1,
	          subdomain2: value2,
	          ...
          },
          "admins":{  // (Object) List of key, value pairs of administrators.
			  alias1: <Administrator address>,
			  alias2: <Administrator address>,
			  ...
          },
          "tfdetail":{
	          price: <Price>,  // (int) Listing price of a domain.
	          buyer: <Address>,  // (string) Buyer address.
	          expire: <Timetamp>,  // (int) Expired timestamp of a transfer command.
	          seller: <Address>,  // (string) Seller address.
	          tx: <tx>,  // (string) Hash of the transaction which will used to accept a domain transfer.
		  }
       }
    }

Developers are also able to query a subdomain/key for nbdomain.

    curl https://manage.nbdomain.com/node/?nid=key1.example.test

The response of  HTTP API looks like the following:

    {
        "code":0,  // (int) Response code of the request.
        "message":"SUCCEED",  // (string) Response message.
        "obj":"111"  // (string) value of the subdomain.
        
    }
|VALUE|RESPONSE CODE|
|---|--|
|0  |`NO_ERROR`|
|14 |`ERROR_NID_NOT_VALID`|
|16 |`ERROR_NOTFOUND`|
|100|`ERROR_UNKNOWN`|


# More
For more information, please follow Maxthon browser on [twitter](https://twitter.com/Maxthon).
