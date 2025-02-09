# simple-systemd-service
This is a simple systemd service example for a bash script

Enter this command to write your systemd code:

```sudo nano /etc/systemd/system/example.service```

```
[Unit]
Description=My Service
After=network.target

[Service]
ExecStart=bash /root/example.sh
WorkingDirectory=/root/
StandardOutput=inherit
StandardError=inherit
Restart=always
User=root

[Install]
WantedBy=multi-user.target
```

```
sudo systemctl daemon-reload
sudo systemctl start example.service
sudo systemctl enable example.service
sudo systemctl status example.service
```
