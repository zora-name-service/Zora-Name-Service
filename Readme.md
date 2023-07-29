# Zora Name Service for Zora
This document will help you incorporate .zora into your projects. In the document, available functions are examined by including web3.js and .zora name service in your project.


### Requirements
>If you are not actively using it in your project, you should install web3.js.

**NODE**
```
npm install web3
```

**YARN**
```
yarn add web3
```

**In the Browser**
```javascript
<script src="https://cdn.jsdelivr.net/npm/web3@latest/dist/web3.min.js"></script>
```
or
```javascript
<script src="https://unpkg.com/web3@latest/dist/web3.min.js"></script>
```

### Installation

**NODE**
```
npm i zoranameservice
```

**In the Browser**
```javascript
<script src="https://www.unpkg.com/zoranameservice@1.0.0/index.js"></script>
```


### Usage
First, we connect with the libraries.

```javascript
const web3 = new Web3(Web3.givenProvider)
// First create a web3js provider

const zoraNS = new zoraNS(web3)
// You are now ready for .zora
```

## GETS

**Primary Address (Ethereum Address to .zora Name)**

Returns the primary address registered to this address.
```javascript
zoraNS.primaryAddress("ETH_ADDRESS")
.then(function(result){
    console.log(result)
    // Returns the primary address registered to this address.
})
```

**Resolve Address  (.zora Name to Ethereum Address)**

Returns the resolved ethereum address of the .zora name.
```javascript
zoraNS.resolveAddress("name.zora").then(function(result){
    console.log(result)
    // Returns the resolved ethereum address of the .zora name.
})
```

**Address Owners**

Returns the domains owned by an address.
```javascript
zoraNS.addressOwners("ETH_ADDRESS").then(function(resultOwners){
	console.log(resultOwners)
})
```  

**Last registered names**

Returns the last  registered .zora names
```javascript
zoraNS.lastAddresses(20).then(function(result){
    console.log(result)
    //Returns the last 10 registered .zora name
})
```

**Is this domain name taken ?**

Returns whether a domain name has been registered by another user.
```javascript
zoraNS.isTaken("zora").then(function(resultTaken){
    if (resultTaken>0) {
        //This domain name has been registered.
    }
})
```


**Get Data**

Get domain name information.
```javascript
zoraNS.getData("name","data_name").then(function(result){
    console.log(result)
});
```


**Get Twitter Account**

Get Twitter account from .zora name.
```javascript
zoraNS.getTwitter(name).then(function(account_twitter){
     console.log(account_twitter)
})
```


**Get Instagram Account**

Get Instagram account from .zora name.
```javascript
zoraNS.getInstragram(name).then(function(account_instagram){
     console.log(account_instagram)
})
```

**Get Discord Account**

Get Discord account from .zora name.
```javascript
zoraNS.getDiscord(name).then(function(account_discord){
     console.log(account_discord)
})
```

**Get Telegram Account**

Get Telegram account from .zora name.
```javascript
zoraNS.getTelegram(name).then(function(account_telegram){
     console.log(account_telegram)
})
```

**Get URL**

Get URL from .zora name.
```javascript
zoraNS.getUrl(name).then(function(account_url){
     console.log(account_url)
})
```

**Get Email**

Get Email from .zora name.
```javascript
zoraNS.getEmail(name).then(function(account_email){
     console.log(account_email)
})
```


**Get Description**

Get Description from .zora name.
```javascript
zoraNS.getDescription(name).then(function(account_description){
     console.log(account_description)
})
```

**Get Avatar**

Get Avatar from .zora name.
```javascript
zoraNS.getKeywords(name).then(function(account_keywords){
     console.log(account_keywords)
})
```

## SETS

**Set New Primary Address**

Changes the primary address.
```javascript
zoraNS.setPrimaryAddress("name.zora","OWNER_ETH_ADDRESS").then(function(result){
    if (result['status']) {
     //Successful
     } else {
     //Failed
     }
})
```

**Set New Resolve Address**

Changes the resolve address.
```javascript
 zoraNS.setResolveAddress("name.zora","NEW_RESOLVE_ETH_ADDRESS", "OWNER_ETH_ADDRESS").then(function(result){
        if (result['status']) {
        //Successful
        } else {
        //Failed
        }
 })
```

**Register Domain**

Registers a new .zora address and returns the result.
```javascript
zoraNS.register("name.zora",YOUR_REF_ADDRESS,YOUR_ETH_ADDRESS,"3000000000000000").then(function(result){
    if (result['status']) {
        // Registration Successful
    } else {
        // Registration Failed
    }
})
```


**Set Data**

It allows you to add data for the domain name you have.
```javascript
zoraNS.setData("name","data_type","data_value", "Owner_Eth_Address").then(function(result){
    if (result['status']) {
     //Successful
     //eq: data_name: twitter, data_value: twitter_account
     } else {
     //Failed
     }
})
```
