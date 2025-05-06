# -Certbot-Installation-Wildcard-Domain-Certificate-Guide-

## step 1:  Using apt (Debian/Ubuntu only)
```
sudo apt update
sudo apt install certbot
```
### Step 2: Generate a Wildcard SSL Certificate

This uses a manual DNS-01 challenge, suitable when DNS API integration is unavailable.
Run:
```
certbot --server https://acme-v02.api.letsencrypt.org/directory \
  -d *.yourdomainname.com \
  --manual \
  --preferred-challenges dns-01 \
  --key-type rsa \
  certonly
```
You’ll be prompted to:

  1.  Create a DNS TXT record for _acme-challenge.yourdomainname.com

  2.  Enter the TXT value provided by Certbot into your DNS provider’s panel

  3.  Wait for DNS propagation (use https://dnschecker.org to confirm)

    Press Enter when ready

   ##  Step 3: Certificate File Locations

Certbot will store certificates here (by default):

    Certificate: /etc/letsencrypt/live/omnicloudapi.com/fullchain.pem

    Private Key: /etc/letsencrypt/live/omnicloudapi.com/privkey.pem

    Chain only: /etc/letsencrypt/live/omnicloudapi.com/chain.pem


