# Let's Encrypt

Let’s Encrypt is a free, automated, and open certificate authority brought to you by the non-profit Internet Security Research Group (ISRG).

## Installing Let's Encrypt

We need to start by updating the local server's apt package indexes

`sudo apt-get update`

We can now install the Let's Encrypt Client

`sudo apt-get install letsencrypt`

## Obtaining the certificate

`sudo letsencrypt certonly --standalone --email youremail@example.com -d yourdomain.com`

After running this command  a few dialogs will appear. Follow their instructions until you reach the end.

The output should look similar to this one below.

```
IMPORTANT NOTES:
 - If you lose your account credentials, you can recover through
   e-mails sent to sammy@digitalocean.com
 - Congratulations! Your certificate and chain have been saved at
   /etc/letsencrypt/live/example.com/fullchain.pem. Your
   cert will expire on 2016-03-15. To obtain a new version of the
   certificate in the future, simply run Let's Encrypt again.
 - Your account credentials have been saved in your Let's Encrypt
   configuration directory at /etc/letsencrypt. You should make a
   secure backup of this folder now. This configuration directory will
   also contain certificates and private keys obtained by Let's
   Encrypt so making regular backups of this folder is ideal.
 - If like Let's Encrypt, please consider supporting our work by:

   Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
   Donating to EFF:                    https://eff.org/donate-le

```

You will now have four PEM-encoded files in the following location

`/etc/letsencrypt/live/yourdomain.com`

Files:

* **cert.pem**: Your domain's certificate
* **chain.pem**: The Let's Encrypt chain certificate
* **fullchain.pem**: cert.pem and chain.pem combined
* **privkey.pem**: Your certificate's private key