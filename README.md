# bitcoin-wallet-Node.Js

var express = require('express');
var router = express.Router();  
const CryptoAccount = require("send-crypto");
/* GET home page. */
 
router.get('/', async function(req, res, next) {
 
 
/* Load account from private key */
// const privateKey = process.env.PRIVATE_KEY || CryptoAccount.newPrivateKey();
const privateKey = "7a057bc9043cb615d4b255833e8ed50bdd133bc7c1233f5fb997e8f6a8133a65"; 
const account = new CryptoAccount(privateKey, {
    network: "testnet",
});

/* Print address */
console.log("Dear Rahul Your Bitcoin Account is  \n"+await account.address("BTC"));
// > "1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa"

/* Print balance */
console.log("\nYour BTC balance is = "+await account.getBalance("BTC"));
// > 0.01

/* Send 0.01 BTC */
// const txHash = await account
//     .send("muzrdi7vhYhe3phgtSX2zJabAZLrhi1Mby", 0.0001, "BTC")
//     .on("transactionHash", console.log) 
//     .on("confirmation", console.log);
  
 

  
});
module.exports = router;
