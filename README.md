# Welcome

{% hint style="info" %}
For better performance, you'll only find information about the stable branch of the API.
{% endhint %}

## Installation

If you'd like to install the Kronix API, please run the following command in your terminal; `npm install kronix.js`

## Example

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
const Kronix = require("kronix.ks");
const config = require("./config.json");
const client = new Kronix.Session({
    token: config.token,
    shardId: 0,
    shardCount: 0
});

client.onListenerEvent("ready", function() {
    console.log(`Successfully logged in as ${client.user.username}#${client.user.discriminator} and on ${client.guilds.size} guilds.`);
});
```
{% endcode-tabs-item %}
{% endcode-tabs %}

This particular example does the following:

* Logs the client in.
* Sets the amount of shards specified.
* Gets the amount of shards specified.
* Triggers the ready listener.

This example also assumes that you have a configuration file. If not, you can just set the `config.token` part to just a normal string.

