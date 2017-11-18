## Description
This is a simple Python script that renew the IP of a local or distant TOR proxy using TOR control port.
You can choose the country of the new exit node using `-c <COUNTRY_CODE>` (you can get a list of the country codes by passing the `--help` flag).

### Installation
- Download the script in your bin folder using `wget https://raw.githubusercontent.com/aeddi/tor_renew_ip/master/tor_renew_ip -P /usr/local/bin`
- Make the script executable using `chmod +x /usr/local/bin/tor_renew_ip`
- Add this line to your torrc `ControlPort 9051`
- Choose a password using `echo HashedControlPassword $(tor --hash-password <PASSWORD>) > <YOUR_TORRC_PATH>`
- (Optionnal) If you want to control your TOR proxy from a remote host, add this line to your torrc `ControlListenAddress <REMOTE-IP>:9051`
- Set an env variable called *TOR_CONTROL_PASSWD* containing your TOR control password (using `export` in your bashrc or whatever)
- (Optional) You can use a custom port and IP for the proxy and/or for the control port by setting the following env variables: *TOR_SOCKS_PORT*, *TOR_SOCKS_HOST*, *TOR_CONTROL_PORT* and *TOR_CONTROL_HOST*
