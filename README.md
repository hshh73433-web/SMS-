
⚡ ETHBD Telegram Fast Forwarder

A powerful and fast Telegram Message Forwarding Tool built with Python and "Telethon" (https://github.com/LonamiWebs/Telethon).

Designed for users who need to transfer Telegram posts/messages from one channel or chat to another using a Telegram user account, with support for media, captions, session persistence, progress tracking, retry handling, and FloodWait protection.

«⚠️ Disclaimer: This project is intended for legitimate automation, migration, backup, and administrative purposes. Use it only with accounts, chats, channels, and content that you are authorized to access or transfer. The developer is not responsible for misuse.»

---

✨ Features

- ⚡ Fast Telegram message forwarding
- 📥 Forward messages from a source chat/channel
- 📤 Send messages to a target chat/channel
- 🖼️ Supports photos, videos, documents, and other media
- 📝 Preserves text/captions when possible
- 🔢 Forward messages by custom "START_ID" and "END_ID"
- ⏱️ Custom forwarding delay
- 🔐 Telegram 2FA support
- 💾 Persistent Telegram session
- ⚙️ Automatically saves API credentials locally
- 🚀 Automatic login using saved session
- 🔍 Fast dialog/entity cache
- 🔄 Automatic retry system
- 🛡️ FloodWait handling
- 📊 Real-time forwarding progress
- ❌ Failed-message tracking
- 🧹 Automatic temporary-file cleanup
- 🎨 Terminal UI with colored output
- 📱 Termux friendly
- 🐧 Linux friendly
- 🔗 Automatically opens the project/community Telegram channel

---

🖥️ Preview

⚡ TELEGRAM FAST FORWARDER v2.0 ⚡

🔐 Enter your password to continue:
📌 Password: ********

✅ Password verified! Access granted.

📌 API ID: ********
📌 API HASH: ********
📌 Phone (+880...): +880XXXXXXXXXX

🔐 Logging in...
✅ Login successful! Session saved.

📋 CONFIGURATION

📌 Source (ID / username / link): @source
📌 Target (ID / username / link): @target
📌 START_ID: 1
📌 END_ID: 100
📌 Delay: 0.3

🚀 Start? (y/n): y

▶️ Starting forward...

✅ 1 → 1/100 (1.0%)
✅ 2 → 2/100 (2.0%)
...
🎉 Complete! 100 saved, 0 failed.

---

🧰 Requirements

Before running the project, make sure you have:

- Python 3.9+
- Telegram account
- Telegram API ID
- Telegram API Hash
- Internet connection
- Access to the source and target chat/channel

---

🔑 Get Telegram API Credentials

You need your own Telegram API credentials.

1. Visit "my.telegram.org" (https://my.telegram.org/)
2. Log in with your Telegram account.
3. Open API development tools.
4. Create an application.
5. Copy your:
   - "API ID"
   - "API Hash"

«🔒 Never publish your "API Hash", phone number, session file, or other private credentials publicly.»

---

📥 Installation

1. Clone the repository

git clone https://github.com/cyberarafatofficial/FORWARD-RESTRICTED-SMS.git

2. Enter the project directory

cd FORWARD-RESTRICTED-SMS

3. Install dependencies

pip install -r requirements.txt

If "requirements.txt" is not available:

pip install telethon requests

---

▶️ Run

Start the program with:

python main.py

For some systems:

python3 main.py

---

📱 Termux Installation

This project can also be used on Android through Termux.

Update packages

pkg update && pkg upgrade -y

Install Python and Git

pkg install python git -y

Clone the repository

git clone https://github.com/cyberarafatofficial/FORWARD-RESTRICTED-SMS.git

Install dependencies

pip install -r requirements.txt

Run

python main.py

---


⚙️ Configuration

The application automatically creates:

config.json

Example:

{
    "api_id": 12345678,
    "api_hash": "YOUR_API_HASH",
    "phone": "+880XXXXXXXXXX"
}

The Telegram session is stored as:

forwarder_session.session

config.json
*.session

Add them to ".gitignore".

---


🗂️ Project Structure

FORWARD-RESTRICTED-SMS/
│
├── main.py
├── requirements.txt
├── README.md
│
├── config.json              # Generated locally
├── forwarder_session.session # Generated locally
│
└── temp_files/              # Temporary media files

---

📦 Requirements.txt

Recommended "requirements.txt":

Telethon
requests

Install everything with:

pip install -r requirements.txt

---

🚀 How It Works

The forwarding process follows this workflow:

Start
  │
  ▼
Password Verification
  │
  ▼
Load Saved Session
  │
  ├── Session Found ──► Auto Login
  │
  └── No Session ─────► Manual Login
                           │
                           ▼
                     Telegram Login
                           │
                           ▼
                    Build Dialog Cache
                           │
                           ▼
                    Source & Target
                           │
                           ▼
                    Message ID Range
                           │
                           ▼
                    Download Media
                           │
                           ▼
                    Send to Target
                           │
                           ▼
                     Retry on Error
                           │
                           ▼
                    Continue Forwarding
                           │
                           ▼
                         Done

---

📌 Supported Source/Target Formats

The program can resolve Telegram entities using:

Username

@shadoow_byte

Telegram Link

https://t.me/Ethical_Hackers_BD

Numeric ID

-1003708091257

---

🔢 Message ID Range

You can specify the exact message range.

Example:

START_ID: 100
END_ID: 500

The tool will attempt to process:

100 → 500

If the values are reversed, the program automatically swaps them.

---

⏱️ Delay

You can set a custom delay between messages.

Example:

Delay: 0.3

This means approximately:

Message → Wait 0.3s → Message → Wait 0.3s

A reasonable delay is recommended to reduce the chance of Telegram rate limiting.

---

🛡️ FloodWait Protection

Telegram may temporarily restrict requests when too many actions are performed.

The tool detects:

FloodWaitError

and automatically waits for the required amount of time before continuing.

Example:

⏳ Flood 25s...

After the wait:

▶️ Continue forwarding...

---

🔄 Retry System

Failed sends are automatically retried up to 3 times.

Attempt 1
   ↓
Failed
   ↓
Attempt 2
   ↓
Failed
   ↓
Attempt 3
   ↓
Success / Failed

---

📊 Progress Tracking

During forwarding, the application displays:

- Current message ID
- Number of forwarded messages
- Total messages
- Completion percentage
- Failed messages
- Total execution time

Example:

✅ 125 → 75/100 (75.0%)

---

🧹 Temporary Files

Media files are temporarily downloaded into:

temp_files/

After successful processing, temporary files are automatically removed.

This helps prevent unnecessary storage usage.

---

🔐 Security

Never share:

API ID
API Hash
Phone Number
Telegram Session
Firebase Credentials
Passwords
config.json

A Telegram ".session" file can potentially provide access to an authenticated Telegram account.

Treat it like a password.

---

⚠️ Important Limitations

This project does not guarantee that every Telegram message can be copied.

Possible reasons for failure include:

- Private chats/channels
- Missing permissions
- Deleted messages
- Restricted content
- Telegram API restrictions
- Invalid message IDs
- Flood limits
- Network failures
- Unsupported media
- Account restrictions

---

⚖️ Responsible Use

Use this project only for content and Telegram accounts you are authorized to manage.

Do not use it to:

- Spam users or channels
- Circumvent Telegram restrictions
- Copy private content without permission
- Abuse Telegram's API
- Distribute unauthorized copyrighted material
- Perform mass unsolicited messaging

You are responsible for complying with Telegram's rules and applicable laws.

---

🐛 Troubleshooting

"ModuleNotFoundError"

Install the dependencies:

pip install -r requirements.txt

Or:

pip install telethon requests

---

Login Problems

Make sure:

API ID       → Correct
API HASH     → Correct
Phone        → Includes country code

Example:

+8801XXXXXXXXX

If your account has 2FA enabled, enter the 2FA password when requested.

---

Source Not Found

Make sure:

- You are a member of the source channel/group.
- The username is correct.
- The Telegram link is valid.
- The message IDs exist.

---

Target Not Found

Make sure the Telegram account has permission to send messages to the target.

---

FloodWait

If you receive a FloodWait message, do not repeatedly restart the program.

The application automatically waits and continues when possible.

---

💡 Performance Tips

For better reliability:

Use a stable internet connection
        +
Use a reasonable delay
        +
Avoid unnecessary repeated restarts
        +
Keep your Telegram session secure

For large transfers, use a conservative delay rather than trying to maximize speed.

---

🤝 Contributing

Contributions are welcome.

Fork the repository

git fork

Or use GitHub's Fork button.

Clone your fork

git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git

Create a branch

git checkout -b feature/my-feature

Commit your changes

git add .
git commit -m "Add new feature"

Push

git push origin feature/my-feature

Then open a Pull Request.

---

📝 Feature Requests

Have an idea?

Open a GitHub Issue and describe:

Feature:
Why it is useful:
How it should work:
Expected behavior:

---

🐞 Bug Reports

When reporting a bug, include:

Operating System:
Python Version:
Telethon Version:
Error Message:
Steps to Reproduce:

Never include your API Hash, phone number, password, or session file.

---

📜 License

This project is provided for educational and legitimate automation purposes.

You may modify and use the project according to the terms specified in the repository's license.

If you add a formal open-source license, replace this section with the exact license text and license badge.

---

👨‍💻 Developer

ETHBD

Telegram Community:

https://t.me/Ethical_Hackers_BD

---

⭐ Support the Project

If this project helped you:

⭐ Star the repository
🍴 Fork the project
🐛 Report bugs
💡 Suggest features
🤝 Contribute improvements

---

⚡ Final Note

ETHBD Telegram Fast Forwarder v2.0

Built with:

Python
   +
Telethon
   +
Firebase REST API
   +
AsyncIO

«🚀 Fast • Simple • Reliable • Termux Friendly»

---

📌 Disclaimer

This software is provided "as is", without warranty of any kind.

The developer is not responsible for:

- Account restrictions
- Telegram API limitations
- Data loss
- Misuse of the software
- Unauthorized content transfers
- Violation of Telegram policies
- Violation of local or international laws

Use responsibly and only with content/accounts you are authorized to manage.
