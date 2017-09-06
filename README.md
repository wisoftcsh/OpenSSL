Create OpenSSL
===========================

The basics command line steps to generate a private and public key using OpenSSL are as follow

```
openssl genrsa -out private.key 1024

openssl req -new -x509 -key private.key -out publickey.cer -days 365

openssl pkcs12 -export -out public_privatekey.pfx -inkey private.key -in publickey.cer
```

Step 1 – generates a private key

Step 2 – creates a X509 certificate (.cer file) containing your public key which you upload when registering your private application (or upgrading to a partner application).

Step 3 – Export your x509 certificate and private key to a pfx file. If your chosen wrapper library uses the .pem file to sign requests then this step is not required.

Hope that helps! This answer explains the different file extensions.
