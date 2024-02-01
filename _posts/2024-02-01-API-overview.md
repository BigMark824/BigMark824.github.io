# GooberBlox API

Hey everyone, just wanted to do a quick overview on the APIs available on GooberBlox!

**Base URL:** [https://goober.biz/v1/](https://goober.biz/v1/)

# GET APIs

### User API
[https://goober.biz/v1/users/?id={id}](https://goober.biz/v1/users/?id={id})
```json
{
	"ID": 1,
	"Username": "ROBLOX",
	"Admin": true,
	"Description": "This is the official GOOBERBLOX account!",
	"CreationDate": "2023-11-19",
	"Online": true,
	"Membership": "BuildersClub",
	"Banned": "0"
}
```

### Presence API
[https://goober.biz/v1/presence/users/?id={id}](https://goober.biz/v1/presence/users/?id={id})
Warning! This is incomplete!
```json
{
	"UserPresencesType": "0",
	"LastLocation": "null",
	"placeID": "null",
	"rootPlaceID": "null",
	"gameId": "null",
	"userId": "1",
	"LastOnline": "2024-02-01"
}
```

### Site Statistics
[https://goober.biz/v1/stats/](https://goober.biz/v1/stats/)
```json
{
	"data": {
		"users_reg_today": "5",
		"users_reg_yesterday": "5",
		"user_count": "756",
		"users_online_broken": "12",
		"server_time": 1706773083
	}
}
```

### Game API
[https://goober.biz/v1/game/?id={id}](https://goober.biz/v1/game/?id={id})
```json
{
	"ID": 1,
	"Creator": "ROBLOX",
	"Name": "Natural Disaster Survival",
	"Created": "2023-11-17",
	"Updated": "2023-11-17"
}
```


# POST APIs

### As of now there are no publicly available POST APIs, only internal ones!

# Site tests
[https://goober.biz/v1/test/{api}](https://goober.biz/v1/test/{api})
This is where I publicly test APIs before deploying them!

### Authentication [<span style="color:Tomato">BaseURL</span>/<span style="color:green">Test/NewAuth</span>]

#### Return Types:
Error [<span style="color:red">400 Bad Request</span>]:

```json
{
	"message:": "User not logged in."
}
```

Success [<span style="color:green">200 OK</span>]:

```json
fHD6Bjsn2rrkp9O7iL4xPKhFvNMut9TKJPeXPv0N8V6pL51Kd6bOc0gpDAI8TUcC7XlnJ0TQF3dKIQBK7ipBLrHrKLa7UVxfWVWE5FeQGYXscaQu/DCwBIk1W9NV9+u7+GG77CTr1arfpzBnFUNtZqUiq8kxcMtDeCzspsVbBK398fB+6SmmcRFDY03cpisT7LkiwhEJPYkGHdkquhapWggCFz7IlPbbKtguuKb3nRky0xws8jcbqB0Kp2IODUW7HlQqpp9RFAi+ZXkrT7FTYjDvD9zXLrPHcA81v5yPklv3aeJQNBDlUNE54DRyLAXZRbKXbBP440d8b9P6A4lsOw==
```

Upon succession the site will generate a sha256 + base64ed token that validates their login to the Game Client based on their session token and the internal Private Key.