User information
==========

`GET /me.json` will return with your information, some preferences and a list of your accounts. You’ll need those ID-s to make other calls.


```json
{
	"colorblind":false,
	"email":"email@example.com",
	"id":1234567,
	"initials":"un",
	"name":"User Name",
	"avatar_url":"/images/profile_small.png",
	"large_avatar_url":"/images/profile_large.png",
	"micro_avatar_url":"/images/profile_micro.png",
	"avatar_background":"#1e6da1",
	"has_avatar":false,
	"accounts":[
		{
			"weight":0,
			"dummy":true,
			"id":1234567,
			"subdomain":"account1"
		},
		{
			"weight":1,
			"dummy":false,
			"id":1234567,
			"subdomain":"account2"
		}
	]
}
```