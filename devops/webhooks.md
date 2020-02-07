# Webhooks

[Source: the Zapier guide to webhooks](https://zapier.com/blog/what-are-webhooks/)

Webhooks == apps sending automated messages or information to other apps.

They get sent automatically when something happens; they contain a payload (message; essentially like params) set to a unique URL (like your app's phone number or address).

Usually sent via HTTP GET request - adding the data to the URL, then pinging that URL. Example: `https://yourapp.com/data/12345?Customer=bob&value=10.00&item=paper`.

> Technically, webhooks are "user-defined callbacks made with HTTP" according to Jeff Lindsay, one of the first people to conceptualize webhooks.

> They're called webhooks since they're software hooks—or functions that run when something happens—that work over the web.

Webhooks typically are used to connect two different applications. 

An event happens on the trigger application -> it serializes data about that event and -> sends it to a webhook URL from the action application—the one you want to do something based on the data from the first application; -> the action application can then send a callback message, often with an `HTTP` status code like `302` to let the trigger application know if the data was received successfully or `404` if not.

Webhooks are similar to APIs but simpler.

### Webhooks tools:

* [Request Bin - to inspect HTTP events](https://requestbin.com/) - lets you create webhooks URLs and send data to see how it's recognised
* 

