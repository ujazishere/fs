Spin it up `docker compose up -d`
1. Tunnel using ngrok
2. Transfer files from local machine to homelab. homelab is the one exposed using ngrok to share files

### 1. Tunnel using ngrok - Optional(Have tried this for frontend and backend with CORS errors - unable to resolve)
signup/ on https://dashboard.ngrok.com/

Use auth key from the ngrok web to authenticale ubuntu,

Specify port you want to tunnel - in this case 8080(verify where youre exposing using `curl`) for the simple python webserver. For example `ngrok http 8080`

Wait a few mins and Viola it will be exposed - use the link on ngrok's `Endpoints & Traffic Policy` to get the url it will be exposed to -> https://dashboard.ngrok.com/endpoints

### 2. Transfer files using Secure copy - `scp`
Copy file from local to homelab
```
scp /path/to/local/file user@tailscale-ip:/path/on/homelab/
```

Copy directory (recursively)
```
scp -r /path/to/local/dir user@tailscale-ip:/path/on/homelab/
```
