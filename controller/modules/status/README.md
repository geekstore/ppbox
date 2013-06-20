Status module
======================
This module is responsible for handling all status requests. The status module is used to confirm whether a payment made by 
customer using PayPal is success or failure.

Class Status
--------------
This Status class represents the main status controller. 
For example, <br><br>
`public function get_email($req)` <br><br>
is a HTTP get method handler for getting the payment's status of email checkout.

Getting Payment's status
---------------------------
Use a HTTP GET request of status resource to check , what is happening with your payment in your account history.

<b>Creating and Managing Classic API Credentials :</b>
When calling this api, you must authenticate each request using a set of API credentials. PayPal associates a set of API credentials with a specific PayPal account, and you can generate credentials for any PayPal Business or Premier account.
This guide describes how to create the credentials you need to make calls.<br>

* Live account: https://developer.paypal.com/webapps/developer/docs/classic/api/apiCredentials/ <br>
* Sandbox account:   https://developer.paypal.com/webapps/developer/docs/classic/lifecycle/ug_sandbox/ <br>

###Request (Sample for `Accept` = `json`):<br>###
REST URL: `http://<hostname>/ppbox/rest/status` <br>
HTTP Method: GET <br>
Headers: <br>
`method` = `email` <br>
`Accept` = `json` <br>
URL params: <br>
<pre>
`live` = `false` 
`api_username` = `mer102_1362122176_biz_api1.gmail.com` 
`api_password` = `1362122231` 
`api_signature` = `AjsbJc8Z7bMatF-pWQPqoJdMdJ4AAf70D6iap-C787dthlUmSAbwoCv-` 
`api_appid` = `APP-80W284485P519543T`
`payKey` = `AP-57H06625C1355893W` 
</pre>


###Response (Sample for `Accept` = `json`):<br>###
<pre>
{{
    "status": "success",
    "data": [
        {
            "email": "mer101_1359454882_biz@gmail.com",
            "status": "COMPLETED"
        },
        {
            "email": "merchant201_biz@gmail.com",
            "status": "COMPLETED"
        },
        {
            "email": "merchant202_biz@gmail.com",
            "status": "COMPLETED"
        }
    ]
}
</pre>

###Request (Sample for `Accept` = `xml`):<br>###
REST URL: `http://<hostname>/ppbox/rest/status` <br>
HTTP Method: GET <br>
Headers: <br>
`method` = `email` <br>
`Accept` = `xml` <br>

URL params: <br>
<pre>
`live` = `false` 
`api_username` = `mer102_1362122176_biz_api1.gmail.com` 
`api_password` = `1362122231` 
`api_signature` = `AjsbJc8Z7bMatF-pWQPqoJdMdJ4AAf70D6iap-C787dthlUmSAbwoCv-` 
`api_appid` = `APP-80W284485P519543T`
`payKey` = `AP-57H06625C1355893W` 
</pre>


###Response (Sample for `Accept` = `xml`):<br>###
<pre>
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;root&gt;
    &lt;status&gt;success&lt;/status&gt;
    &lt;data&gt;
        &lt;0&gt;
            &lt;email&gt;mer101_1359454882_biz@gmail.com&lt;/email&gt;
            &lt;status&gt;COMPLETED&lt;/status&gt;
        &lt;/0&gt;
        &lt;1&gt;
            &lt;email&gt;merchant201_biz@gmail.com&lt;/email&gt;
            &lt;status&gt;COMPLETED&lt;/status&gt;
        &lt;/1&gt;
        &lt;2&gt;
            &lt;email&gt;merchant202_biz@gmail.com&lt;/email&gt;
            &lt;status&gt;COMPLETED&lt;/status&gt;
        &lt;/2&gt;
    &lt;/data&gt;
&lt;/root&gt;

</pre>
