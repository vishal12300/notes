
# Get notified on discord whenever you have an SSRF or Open Redirect 

It creates a URL which is useful for finding SSRF, open redirect and HTTP request triggered issues. When the server hits your server the following script sends the message to the discord server with visitor details. 


It is some kind of alternative to burp collaborator or requestbin, It is live 24/7. But it only provide the HTTP request triggered, You may be miss the DNS query requests.

## PHP Code

```
<?php
date_default_timezone_set('Asia/Kolkata'); 

$date = date('Y-m-d H:i:s');


$ip_address = $_SERVER['REMOTE_ADDR'];

$user_agent = $_SERVER['HTTP_USER_AGENT'];

$endpoint = $_SERVER['REQUEST_URI'];

$log_message = "**Seems like you have a HIT**\n```Date: $date\t\nIP: $ip_address\t\nUser-Agent: $user_agent\t\nPath: $endpoint```\n";

// echo $log_message;
echo "<body><h1>Ok, Health Check </h1></body>";


$webhook_url = "https://discord.com/api/webhooks/1093588418959798292/aZo7X4TisqrQxRSHtbvutlQ3AFmhA4ZrhmoxRnHx-aQ5BcK9WFxYxSm7oeOLTv2YK8T"; // replace with your webhook URL
$message = array("content" => "$log_message"); // the message you want to send

$ch = curl_init($webhook_url);
curl_setopt($ch, CURLOPT_HTTPHEADER, array('Content-type: application/json'));
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($message));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_exec($ch);
curl_close($ch);

?>
```

## Refresnce 
I find this from the following medium blog 
[https://medium.com/@a1bi/ssrf-get-notified-on-discord-whenever-you-have-an-ssrf-5162a6daf8a3](https://medium.com/@a1bi/ssrf-get-notified-on-discord-whenever-you-have-an-ssrf-5162a6daf8a3)
