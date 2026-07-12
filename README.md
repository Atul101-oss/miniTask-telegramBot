# 🤖 FileBot — Telegram File Processing Bot

A modular Telegram bot built with Python that provides handy file-processing utilities right inside your chats. Resize images, merge PDFs, and convert images to PDF — all through an intuitive inline-button interface.

---

## ✨ Features

| Tool | Description |
|---|---|
| **🖼️ Resize Image** | Scale images by preset percentages (25%, 50%, 75%) or enter custom dimensions (e.g. `800 x 600`). Supports both compressed photos and uncompressed file uploads. |
| **📄 Merge PDFs** | Collect multiple PDF files one-by-one and merge them into a single document. |
| **🖼️ ➡ 📄 Image to PDF** | Collect multiple images and combine them into a multi-page PDF, one image per page. |

### Additional Highlights

- **Inline button menus** — No need to memorize commands; navigate everything through interactive buttons.
- **Conversation-based flows** — Each tool guides you step-by-step using Telegram's `ConversationHandler`.
- **Robust file handling** — Generous timeouts for large file transfers, format validation, and helpful error messages.
- **Cancel anytime** — Use `/cancel` or the ❌ button to abort any operation and return to the main menu.

---

## 🏗️ Project Structure

```
miniTaskBot/
├── bot.py                  # Entry point — config, handler registration, polling
├── miniTaskBot.py          # (Legacy/scratch starter file)
├── handlers/
│   ├── __init__.py
│   ├── start.py            # /start, /help commands & main menu routing
│   ├── image_resize.py     # Image resize conversation handler
│   ├── pdf_merge.py        # PDF merge conversation handler
│   └── img_to_pdf.py       # Image-to-PDF conversation handler
├── keyboards/
│   ├── __init__.py
│   └── menus.py            # Inline keyboard builders & callback constants
├── utils/
│   ├── __init__.py
│   ├── image_utils.py      # Image resize & image-to-PDF logic (Pillow)
│   └── pdf_utils.py        # PDF merge logic (PyPDF2)
├── requirements.txt        # Python dependencies
├── run_bot.sh              # Shell script to run the bot
└── .env                    # Bot token (not committed)
```

---

## 🚀 Getting Started

### Prerequisites

- **Python 3.10+**
- A **Telegram Bot Token** from [@BotFather](https://t.me/BotFather)

### 1. Clone the Repository

```bash
git clone https://github.com/Atul101-oss/miniTask-telegramBot.git
cd miniTask-telegramBot
```

### 2. Create a Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file in the project root:

```env
BOT_TOKEN=your-telegram-bot-token-here
```

### 5. Run the Bot

```bash
python3 bot.py
```

You should see:

```
🤖 FileBot is running! Press Ctrl+C to stop.
```

---

## 💬 Usage

1. Open your bot in Telegram and send `/start`.
2. The main menu appears with inline buttons for each tool.
3. Tap a tool to begin — the bot walks you through each step.
4. Use `/cancel` or the cancel button at any point to abort and return to the menu.

### Commands

| Command | Description |
|---|---|
| `/start` | Show the welcome message and main menu |
| `/help` | Display detailed usage instructions |
| `/cancel` | Cancel the current operation |

---

## 🧰 Tech Stack

| Library | Purpose |
|---|---|
| [python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot) `>=22.0` | Telegram Bot API wrapper (async) |
| [Pillow](https://pillow.readthedocs.io/) `>=10.0` | Image resizing & image-to-PDF conversion |
| [PyPDF2](https://pypdf2.readthedocs.io/) `>=3.0` | PDF merging |
| [python-dotenv](https://github.com/theskumar/python-dotenv) `>=1.0` | `.env` file loading |

---

## 🤝 Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/awesome-tool`)
3. Commit your changes (`git commit -m "Add awesome tool"`)
4. Push to the branch (`git push origin feature/awesome-tool`)
5. Open a Pull Request

---

## 📄 License

This project is open source. See the repository for license details.
