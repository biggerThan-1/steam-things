steam-market-search
============

[![NPM](https://nodei.co/npm/steam-market-search.png?downloads=true)](https://nodei.co/npm/steam-market-search/)

**What is this?**  
------------
steam-market-search is a NodeJS package for retrieving market information of steam community items for a certain app.
These items are Emoticons, Backgrounds, Trading cards and Booster Packs.

Quick Start
--------------

**Install in your app directory**

```shell
$ npm install steam-market-search --save
```

**Basic usage**
```javascript
var SteamMarket = require('steam-market-search');

// 311210 = Call of Duty: Black Ops III

SteamMarket.getItems({ appid : 311210 }, function(err, res){
    console.log( JSON.stringify(res[0], null, 2) );
});
```

**Output:**

```json
{
  "item_name": "Metro (Foil)",
  "game_name": "Call of Duty: Black Ops III Foil Trading Card",
  "price": {
    "currency": "USD",
    "normal_price": 0.52,
    "sale_price": 0.5
  },
  "link": "http://steamcommunity.com/market/listings/753/311210-Metro%20%28Foil%29",
  "image": "...long image url...",
  "type": "Trading Card"
}
```

**Filtering Results**

You can get specific item types with the following functions

```javascript

SteamMarket.getEmoticons({ appid : 311210 }, function(err, res){});
SteamMarket.getCards({ appid : 311210 }, function(err, res){});
SteamMarket.getBackgrounds({ appid : 311210 }, function(err, res){});

// If you want to get all item types (including boosters), Just use .getItems()

```

**API Lockout!**

If you receive this error, You've been probably been temporarily blocked from the steam API for making too many requests in a short time.
This will go away after a few minutes, But If you don't want to see it again limit the requests you make per minute.
Proxy support will be added in the future.


**Additional Notes**

- Please report any issues [here](https://github.com/TryHardHusky/SteamMarketSearch/issues)