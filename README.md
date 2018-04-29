<p align="center">
  <a href="https://telegram.org/">
    <img height="150" src="https://cdn.worldvectorlogo.com/logos/telegram.svg">
  </a>
  <a href="http://telegraf.js.org/">
    <img height="150" src="https://cdn.rawgit.com/telegraf/telegraf/develop/docs/telegraf.png">
  </a>
</p>

# telegraf-update-logger

> Update logging middleware for [Telegraf](http://telegraf.js.org/)

## Install

```bash
yarn add telegraf-update-logger
```

## Usage

```js
const Telegraf = require('telegraf');
const updateLogger = require('telegraf-update-logger');

const bot = new Telegraf(process.env.BOT_TOKEN);

bot.use(updateLogger());

bot.startPolling();
```

## API

### <code>updateLogger(options: object?): function</code>

Creates a middleware that logs every [update](https://core.telegram.org/bots/api#update) and then invokes the next middleware.

**Params**:

* **`options`** `object?` `= {}`
  * **`.filter`** <code>(update: <a href="https://core.telegram.org/bots/api#update">Update</a>) => boolean</code> – a function that determines which updates should be logged
  * **`.log`** `(formattedUpdate: string) => void` `= console.log` – a function that logs formatted updates
  * **... [`format`](#updateloggerformatupdate-update-options-object-string) options**

### <code>updateLogger.format(update: <a href="https://core.telegram.org/bots/api#update">Update</a>, options: object?): string</code>

Formats an [update](https://core.telegram.org/bots/api#update) as string.

**Params**:

* **`update`** [Update](https://core.telegram.org/bots/api#update)
* **`options`** `object?` `= {}`
  * **`.colors`** `boolean | object` `= false` – enables/disables/sets [colors](https://github.com/chalk/chalk/)
    * **`.id`** `function` – a function that sets colors of message IDs
    * **`.chat`** `function` – a function that sets colors of chat titles
    * **`.user`** `function` – a function that sets colors of user names
    * **`.type`** `function` – a function that sets colors of message types

## Contribute

PRs accepted.

## License

[MIT](LICENSE) © [Dmytro Meleshko](https://github.com/dmitmel)
