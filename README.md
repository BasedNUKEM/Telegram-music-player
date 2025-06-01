# Telegram-music-player

A simple Telegram Bot to manage a queue of music links. Users can add links, and the bot will "play" them by announcing them in the chat.

## Features

* Add music links (e.g., Spotify, YouTube) to a queue.
* Play, skip, and stop music playback.
* View the current music queue.
* View the currently playing track.
* Inline buttons for quick actions (skip, view queue, play first track).
* In-memory queue (lost on restart).

## Setup

1. **Clone the repository (or download the `Telegramcode` file).**

2. **Create a `requirements.txt` file with the following content:**

   ```txt
   python-telegram-bot>=20.0
   ```

3. **Install dependencies:**

   Open your terminal or command prompt in the project directory and run:

   ```sh
   pip install -r requirements.txt
   ```

4. **Set up your Telegram Bot Token:**

   * Talk to [BotFather](https://t.me/botfather) on Telegram to create a new bot and get its token.
   * Set the token as an environment variable named `TELEGRAM_BOT_TOKEN`.
     * On Linux/macOS: `export TELEGRAM_BOT_TOKEN="YOUR_ACTUAL_TOKEN"`
     * On Windows (Command Prompt): `set TELEGRAM_BOT_TOKEN="YOUR_ACTUAL_TOKEN"`
     * On Windows (PowerShell): `$env:TELEGRAM_BOT_TOKEN="YOUR_ACTUAL_TOKEN"`
   * Alternatively, you can hardcode the token in the `Telegramcode` script by replacing `"YOUR_BOT_TOKEN_HERE"` with your actual token, but using an environment variable is recommended for security.

## Running the Bot

Once dependencies are installed and the bot token is set, run the bot using:

```sh
python Telegramcode
```

## Bot Commands

* `/start` - Greets the user and shows a welcome message.
* `/help` - Shows the help message with all available commands.
* `/add <music_link>` - Adds a music link (e.g., Spotify, YouTube) to the queue.
* `/play` - Starts 'playing' music from the queue.
* `/queue` - Shows the current music queue.
* `/skip` - Skips the current track and 'plays' the next one.
* `/nowplaying` or `/np` - Shows the track that's currently 'playing'.
* `/stop` - Clears the queue and stops 'playing'.

## Future Improvements / Considerations

* **Persistence**: Currently, the queue is in-memory and will be lost if the bot restarts. For a more robust bot, the queue could be saved to a file or database.
* **Multi-chat Support**: The current bot uses a global queue. For use in multiple group chats simultaneously, the queue management would need to be per-chat.
* **Track Title Fetching**: Enhance user experience by fetching actual track titles from links instead of just showing the URL.
* **Duplicate Track Prevention**: Add a check to prevent adding the same link multiple times.
* **Admin Controls**: For group usage, consider adding admin-only controls for commands like `/stop` or `/skip`.