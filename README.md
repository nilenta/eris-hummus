Eris for Hummus [![NPM version](https://img.shields.io/npm/v/eris_hummus.svg?style=flat-square&color=informational)](https://npmjs.com/package/eris_hummus)
====

A Node.js wrapper for interfacing with Hummus.

Installing
----------

You will need NodeJS 10.4+. If you need voice support you will also need Python 2.7 and a C++ compiler. Refer to [the Getting Started section of the docs](https://abal.moe/Eris/docs) for more details.

```
npm install --no-optional eris_hummus
```

If you need voice support, remove the `--no-optional`.

Ping Pong Example
-----------------

```js
const Eris = require("eris_hummus");

// Replace TOKEN with your bot account's token
const bot = new Eris("Bot TOKEN", {
    intents: [
        "guildMessages"
    ]
});

bot.on("ready", () => { // When the bot is ready
    console.log("Ready!"); // Log "Ready!"
});

bot.on("error", (err) => {
  console.error(err); // or your preferred logger
});

bot.on("messageCreate", (msg) => { // When a message is created
    if(msg.content === "!ping") { // If the message content is "!ping"
        bot.createMessage(msg.channel.id, "Pong!");
        // Send a message in the same channel with "Pong!"
    } else if(msg.content === "!pong") { // Otherwise, if the message is "!pong"
        bot.createMessage(msg.channel.id, "Ping!");
        // Respond with "Ping!"
    }
});

bot.connect(); // Get the bot to connect to Discord
```

More examples can be found in [the examples folder](https://github.com/nilenta/eris-hummus/tree/master/examples).

Useful Links
------------

- [The GitHub repo](https://github.com/nilenta/eris-hummus) is where development primarily happens.
- [The NPM package webpage](https://npmjs.com/package/eris_hummus) is, well, the webpage for the NPM package.

License
-------

Refer to the [LICENSE](LICENSE) file.
