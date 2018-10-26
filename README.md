# node-vipstarcoin-promise

# Summary

Add Promise support to [node-vipstarcoin](https://github.com/yutotetuota/node-vipstarcoin/blob/master/Readme.md) package.
It is backward compatible with the original package. If no callback function is
passed in to a command a Promise is returned

# Installation

```
npm install vipstarcoin-promise
```

# Example

```
var bitcoin = require( 'vipstarcoin-promise' ) ;

var client = new bitcoin.Client({
  host: 'rcorbish.ydns.eu',
  port: 31916,
  user: 'user',
  pass: 'password',
  timeout: 30000
});

// get a new address and return details about it
client.getNewAddress()
  .then( function(addr){
    return client.validateAddress( addr ) ;
  }) 
  .then( function(addrInfo){
    console.log( addrInfo ) ;
  }) 
  .catch( function(err){
    console.log( err ) ;
  }) ;
```
