# paytags

RAIDA Tech is working with to create a process so that creators of web content could get paid with crypto currency everytime someone clicks on their URL (Like an news artical, video or blog post). For this we think we need a Chrome Browser Plugin. 

The plugin will look at pages for link that say something like:

<apay href="https://premium.com/article.1776623.json" target="_self">News Headline Here</apay>

The Browser plugin would recognize this as a "Premium" link that costs money to click on. When the user clicks on it, the browser would use AJAX to download a json file that may look like this:
```
{
"title":"Tesla Stock Skyrockets",
"price":"100",
"coin":"cloudcoin",
"Author":"Electrek"
"address":"electrek.skywallet.cc"
"memo":"1776623"
}
```
Then the user is prompted "Do you want to pay Electrek 100 CloudCoin for 'Tesla Stock Skyrockets'?"

If the user confirms, the browser uses the "raidajs" javascript class apiPay function to send an AJAX request to the user's wallet to transfer 100 coins to electrek.skywallet.cc.

Then the browser plugin sends a request to the "Premium.com/payment_report page (Already created as a php backend script). The Premium.com/payment_report page returns a "Read Once" token to the browser plugin. This token look like this:
```
{
"cloud":"0",
"splitr":"0"
"sn":"8878343",
"an":[ac557d78,
c692085b,abf14e07,a5fef7a3,4cd81d13,
9cda1537,26a44554,b23d30dc,a801fb65,
bcf65207,8cf24ed7,8c6fe4b,265a8d24c,
6dad9209,fc35437b,bdc6fc89,386c00df,
3daaa5e3,76bb4b21,8a9cbf7b,079ebb1b,
25b3dc57,fff34e1d,bc616039,13a5cd91,
2c6c630a1]
}
```
The browser plugin then uses the raidajs JavaScript class apiView function to get the data from the URL. This data is presented in a new tab or in the current tab depending on the target parameter in the apay tag.   

  



