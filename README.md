# amsakib-career-chatbot

A small chatbot to represent Asir Mosaddek Sakib on his website. The main interactive logic lives in the notebook [notebooks/lab.ipynb](notebooks/lab.ipynb).

Quick references:
- Chat / bot code and tools: [`chat`](notebooks/lab.ipynb), [`send_telegram_message`](notebooks/lab.ipynb), [`record_user_details`](notebooks/lab.ipynb), [`record_unknown_question`](notebooks/lab.ipynb)
- Project config: [pyproject.toml](pyproject.toml)
- Resume/summary used by the bot: [resources/summary.txt](resources/summary.txt)
- Small launcher: [main.py](main.py)
- Environment examples: [.env.example](.env.example) — copy to `.env` and fill secrets. Do not commit `.env` (already in .gitignore).

Prerequisites
- Python 3.12 (see [.python-version](.python-version))
- Recommended: virtual environment

Install
```sh
uv sync
```

Configuration
1. Copy [.env.example](.env.example) -> `.env`.
2. Fill in:
   - OPENAI_API_KEY, OPENAI_API_BASE, OPENAI_DEFAULT_MODEL
   - TELEGRAM_BOT_TOKEN, TELEGRAM_CHAT_ID
3. Confirm `.env` is ignored (it is — see [.gitignore](.gitignore)).

Run the chatbot
- Open and run the notebook [notebooks/lab.ipynb](notebooks/lab.ipynb) in Jupyter/JupyterLab. The notebook launches a Gradio chat UI (`demo.launch()`).
- The notebook contains the main flow and the tools referenced above.

Telegram setup
- Follow the original steps to create a bot with `@BotFather` and obtain `TELEGRAM_BOT_TOKEN`.
- Use `@JsonDumpBot` to get your `TELEGRAM_CHAT_ID`.
- Once configured, the notebook will call [`send_telegram_message`](notebooks/lab.ipynb) to send notifications.

Notes
- The notebook reads the summary from [resources/summary.txt](resources/summary.txt).
- [main.py](main.py) is a minimal entrypoint that prints a message; the interactive chatbot runs from the notebook.
- Dependencies are declared in [pyproject.toml](pyproject.toml).



Telegram bot details instruction
1. Create a new bot using `@BotFather` in telegram. Use `/newbot` to create a new bot. Give a bot name and username when prompted.
Once done, you will be provided with a access token. Copy this token and put it in the `TELEGRAM_BOT_TOKEN=YOUR_TOKEN` in the .env file.

2. To get your chat id, open `@JsonDumpBot` in telegram. Send any message (\start), you will be provided with a json. Copy the id from chat object, and paste it into the .env file as `TELEGRAM_CHAT_ID=your_chat_id`

3. If everything is configured correctly, you will receive message from your bot by using `send_telegram_message` function.