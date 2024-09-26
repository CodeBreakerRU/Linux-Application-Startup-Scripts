### /lib/systemd/system/ts3server

```
[Unit]
Description=TeamSpeak3 Server
Wants=network-online.target
After=syslog.target network.target local-fs.target

[Service]
WorkingDirectory=/home/teamspeak/
User=teamspeak
Group=teamspeak
Type=forking
ExecStart=/home/teamspeak/ts3server_startscript.sh start license_accepted=1
ExecStop=/home/teamspeak/teamspeak/ts3server_startscript.sh stop 
ExecReload=/home/teamspeak/teamspeak/ts3server_startscript.sh restart 
Restart=always
RestartSec=15

[Install]
WantedBy=multi-user.target
```