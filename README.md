## How to register the telegram bot
1. Create a new bot using `@BotFather` in telegram. Use `/newbot` to create a new bot. Give a bot name and username when prompted.
Once done, you will be provided with a access token. Copy this token and put it in the `TELEGRAM_BOT_TOKEN=YOUR_TOKEN` in the .env file.

2. To get your chat id, open `@JsonDumpBot` in telegram. Send any message (\start), you will be provided with a json. Copy the id from chat object, and paste it into the .env file as `TELEGRAM_CHAT_ID=your_chat_id`

3. If everything is configured correctly, you will receive message from your bot by using `send_telegram_message` function.