💧 Water Reminder App — Custom Voice Alerts (PWA)

A smart, installable Progressive Web App (PWA) that reminds you to drink water at selected intervals or specific times — using your own recorded voice as the alarm.
This project supports custom audio, browser notifications, vibration, background alerts, and optional Push Notifications via a Node.js server.

🚀 Features
🔊 Custom Voice Reminder

Plays your own voice recording (alarm.mp3)

Personal and more effective than robotic TTS

Replace audio anytime

⏱ Multiple Reminder Modes

Interval-based (every X minutes)

Daily specific time reminders

Custom labels for each reminder

Pause, resume, delete reminders easily

🔔 Notification Support

Browser Notifications API

Works when app is in background

Mobile vibration support

📱 Installable PWA

Add to home screen (Android / Desktop)

Works offline

Loads instantly

Custom app icons

🛠 Optional Push Server

Node.js push server

Uses web-push + VAPID

Can send reminders even when app is closed

🗂 Tech Stack
Frontend

HTML

CSS

JavaScript (Vanilla)

Notifications API

Audio API (custom MP3)

Vibration API

LocalStorage

Service Worker

Web Manifest (PWA)

Backend (optional)

Node.js

Express.js

Web-Push library

VAPID keys for push notifications

📁 Folder Structure
water-reminder/
├─ public/
│  ├─ index.html
│  ├─ styles.css
│  ├─ app.js
│  ├─ sw.js
│  ├─ sw-register.js
│  ├─ manifest.json
│  ├─ alarm.mp3           # your custom voice
│  ├─ icon-192.png
│  └─ icon-512.png
└─ push-server/
   ├─ server.js
   ├─ package.json
   └─ vapid-keys.json

⚙️ Installation & Setup
1️⃣ Clone the repository
git clone https://github.com/your-username/water-reminder-app.git
cd water-reminder-app

🟦 2️⃣ Start the Push Notification Server (optional)
cd push-server
npm install
node server.js


Server runs on:

http://localhost:3000

🟩 3️⃣ Run the Frontend (PWA)
Option A — VS Code Live Server

Right-click → Open with Live Server

Option B — Node static server:
cd public
npx http-server -p 8000


Open:

http://localhost:8000

🔊 Test Your Voice Alarm

Open Chrome → Press:

Ctrl + Shift + J


Then run:

document.getElementById('alarmAudio').play()


Your personal voice should play.

🔔 Push Notification (Optional)

Trigger a push notification manually:

curl -X POST http://localhost:3000/sendPush \
-H "Content-Type: application/json" \
-d '{"title":"Water Reminder","body":"Time to drink water!"}'

🧠 How It Works
🔹 Reminder Scheduling

Uses JavaScript timers (setTimeout) to trigger reminders at intervals or specific times.

🔹 Audio Playback

Your alarm.mp3 file is played directly using:

alarmAudio.play();

🔹 Notifications

Browser notifications appear even when the tab is in background.

🔹 Service Worker

Handles:

Push events

Background notifications

PWA installation

⚠️ Limitations
Feature	Limitation
Audio autoplay	Requires one user click first
Background reminders	Full support requires push notifications
iOS background alerts	Limited support
Periodic Sync	Experimental; not available everywhere
🌟 Future Improvements

Cloud-based reminder scheduling

User login + data sync

Water intake tracking

Analytics dashboard

Multiple reminder sounds

Dark mode

📜 License

This project is released under the MIT License.
Feel free to use, modify, and distribute.

🙌 Acknowledgements

Web APIs (MDN)

Google Chrome PWA standards

Node.js Web-Push library
