# Discord Webhook Sender

A minimal, single-file web app for sending messages to a Discord channel through a webhook. Set a bot name and avatar, mention a user, role, or everyone, and send, all from the browser.

![Status](https://img.shields.io/badge/status-stable-black?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-black?style=flat-square)
![Languages](https://img.shields.io/badge/languages-EN%20%7C%20RU-black?style=flat-square)

---

## Features

- **Send messages** to any Discord channel via a webhook URL
- **Custom bot name** shown as the sender of each message
- **Per-message avatar** using an image URL
- **Change the webhook avatar** permanently from a local image file (PNG, JPG, GIF, WEBP, up to 8 MB)
- **Mentions** for `@everyone`, `@here`, a specific user, or a role
- **Safe mentions**: `allowed_mentions` is set so only the mention you choose actually pings
- **Bilingual interface** with an English / Russian switch, remembered between visits
- **Clean monochrome design** with smooth animations that respect `prefers-reduced-motion`
- **No build step, no dependencies**: one `index.html` file

## Preview

The interface is a single white page with three cards:

1. **Webhook**: paste your webhook URL
2. **Bot settings**: bot name, optional avatar URL, and avatar upload
3. **Message**: mention type, optional ID, and message text

## Quick Start

### Option 1: Run locally

1. Download or clone this repository.
2. Open `index.html` in any modern browser.

### Option 2: Host on GitHub Pages

1. Push `index.html` to your repository, for example as the `main` branch root.
2. Go to **Settings → Pages**.
3. Under **Source**, select `Deploy from a branch`, choose `main` and `/ (root)`, then save.
4. Your site will be available at `https://<your-username>.github.io/<repository-name>/` after a minute or two.

## How to Get a Webhook URL

1. Open your Discord server and go to **Server Settings → Integrations → Webhooks**.
2. Click **New Webhook**, choose a channel, and copy the **Webhook URL**.

## Getting IDs for Mentions

To mention a specific user or role, you need their numeric ID.

1. In Discord, enable **User Settings → Advanced → Developer Mode**.
2. Right-click the user or role and select **Copy ID**.

Only the `User` and `Role` options require an ID. `@everyone` and `@here` do not.

## Security

> **Treat your webhook URL as a password.** Anyone who has it can post to your channel.

- Do **not** commit your webhook URL to the repository.
- The app sends requests directly from the browser, so the URL is typed in each time and is never stored in the file.
- If your webhook leaks, delete it in Discord and create a new one.
- Avatar changes made through the **Set webhook avatar** button update the real webhook, not just a single message.

## Notes and Limitations

- Discord rate-limits webhooks. Sending many messages quickly can return a `429 Too Many Requests` error.
- Messages are limited to 2000 characters.
- Avatar uploads must be under 8 MB.
- If a request fails, check that the webhook URL is complete and starts with `https://discord.com/api/webhooks/`.

## Project Structure

```
.
├── index.html   # The entire application (HTML, CSS, and JavaScript)
└── README.md    # This file
```

## Contributing

Contributions are welcome. Open an issue to discuss a change, or submit a pull request with a clear description of what you changed and why.

## License

This project is released under the MIT License. See `LICENSE` for details.
