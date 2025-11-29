
🚀 TimeUpdate Systemd Service
A Minimal DevOps Project Demonstrating Linux Service Creation, Automation & Logging




📌 Overview

TimeUpdate is a beginner-friendly Linux DevOps project demonstrating how to create, configure, manage, and monitor a custom systemd service.
The service runs a simple Bash script (timeupdate.sh) that prints the current system time every 10 seconds using journalctl.

This project is excellent for learning:

Linux administration

Systemd unit files

Daemon processes

Logging & monitoring

Automation

Git & GitHub workflow



🧠 Why Systemd Matters (for DevOps)

Systemd is the most widely used init system on modern Linux.
Learning it is essential for:

DevOps Engineers

Cloud Engineers

SRE / Platform Engineers

Backend Engineers

Linux Admin roles

Systemd controls:

Background services

Startup processes

Logging

Daemon lifecycle

Resource limits

Service dependencies

This project demonstrates exactly how production services work under the hood.




/home/dibia/systemd-hello/
│
│── src/
│   └── timeupdate.sh        # Main Bash script executed every 10 seconds
│
│── systemd/
│   └── timeupdate.service   # Custom systemd unit file
│
└── README.md                # Project documentation



1️⃣  Make the script executable
chmod +x /home/dibia/systemd-hello/src/timeupdate.sh

2️⃣  copy the service file to systemd
sudo cp /home/dibia/systemd-hello/systemd/timeupdate.service /etc/systemd/system/timeupdate.service

3️⃣  Reload systemd to detect the new unit
sudo systemctl daemon-reload

4️⃣  Start the service
sudo systemctl start timeupdate.service

5️⃣  Enable the service at boot
sudo systemctl enable timeupdate.service

📝 Viewing Logs

For real-time logs:

journalctl -u timeupdate.service -f


For last 20 logs:

journalctl -u timeupdate.service -n 20

🔍 Troubleshooting

Service status:

sudo systemctl status timeupdate.service -l --no-pager


Restart after any changes:

sudo systemctl daemon-reload
sudo systemctl restart timeupdate.service
