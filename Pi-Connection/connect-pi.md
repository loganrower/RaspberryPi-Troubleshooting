# Connecting Pi to Wifi

## Need to use the 4 files within this folder in order to correctly get onto the wifi

## For hashing use the below method:
reference: https://unix.stackexchange.com/questions/278946/hiding-passwords-in-wpa-supplicant-conf-with-wpa-eap-and-mschap-v2

### obtain the hash with the following
echo -n plaintext_password_here | iconv -t utf16le | openssl md4
### apply hash to the password
password=hash: {OUTPUT OF ABOVE LINE}