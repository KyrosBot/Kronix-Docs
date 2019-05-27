# Simple Command

For this example, we'll be grabbing the example code from the welcome page.

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

However, you can remove the shard parts. Then, your code should look like this:

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
const Kronix = require("kronix.js");
const config = require("./config.json");
const client = new Kronix.Session({
    token: config.token
});
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Now, we're going to be added a message listener.

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
client.onListenerEvent("message", function(message) {
    // This is where our command code will be.
});
```
{% endcode-tabs-item %}
{% endcode-tabs %}

In order to officially finish this example, we will be adding the command.

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
if (message.content === "ping") {
    message.channel.sendMessage("Pong!");
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

In conclusion, your code should turn out as the following;

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
const Kronix = require("kronix.ks");
const config = require("./config.json");
const client = new Kronix.Session({
    token: config.token
});

client.onListenerEvent("ready", function() {
    console.log(`Successfully logged in as ${client.user.username}#${client.user.discriminator} and on ${client.guilds.size} guilds.`);
});

client.onListenerEvent("message", function(message) {
    if (message.content === "ping") {
        message.channel.sendMessage("Pong!");
    }
});
```
{% endcode-tabs-item %}
{% endcode-tabs %}

