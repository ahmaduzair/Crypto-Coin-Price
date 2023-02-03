var btc = document.getElementById("bitcoin")
var eth = document.getElementById("ethereum")
var doge = document.getElementById("dogecoin")
var btc_cap = document.getElementById("bitcoin_cap")
var eth_cap = document.getElementById("ethereum_cap")
var doge_cap = document.getElementById("dogecoin_cap")

var settings = {
    "async": true,
    "scrossDomain": true,
    "url": "https://api.coingecko.com/api/v3/simple/price?ids=bitcoin%2Cethereum%2Cdogecoin&vs_currencies=usd&include_market_cap=true",
    "method": "GET",
    "header": {}
}
$.ajax(settings).done(function (response) {
    btc.innerHTML = response.bitcoin.usd;
    btc_cap.innerHTML = response.bitcoin.usd_market_cap;
    eth.innerHTML = response.ethereum.usd;
    eth_cap.innerHTML = response.ethereum.usd_market_cap;
    doge.innerHTML = response.dogecoin.usd;
    doge_cap.innerHTML = response.dogecoin.usd_market_cap;

});