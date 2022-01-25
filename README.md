# telegraf-group-media for v4

Handle media groups (aka albums) easily with [telegraf](https://telegraf.js.org)!

## Usage
```js
const Telegraf = require('telegraf')
const mediaGroup = require('telegraf-media-group')

const bot = new Telegraf(process.env.BOT_TOKEN)

bot.use(mediaGroup())

bot.on('message', (ctx) => {
  // ctx.mediaGroup — an array of album messages (including the last one)
  for (const message of ctx.mediaGroup) {
    console.log(message)
  }
  return ctx.reply(`total: ${ctx.mediaGroup.length}`)
})
```