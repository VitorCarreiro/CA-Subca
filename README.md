# CA-Subca 

"Easyrsa_root=#" = The machine your root CA
"Easyrsa_subca=#" = The machine your using to do sub-CA

**Build your root CA**
```
Easyrsa_root=# ./easyrsa init-pki
Easyrsa_root=# ./easyrsa build-ca nopass
```
**Build your sub-CA**
```
Easyrsa_subca=# ./easyrsa init-pki
Easyrsa_subca=# ./easyrsa build-ca nopass subca
```
**Get your ca request and place it on easyrsa_root**

`cat /etc/easy-rsa/pki/reqs/ca.req`

**Import the sub-ca with the name sub**

`Easyrsa_root=# ./easyrsa import-req /etc/easy-rsa/pki/reqs/ca.req sub`

**Sign the ca**

`Easyrsa_root=# ./easyrsa sign-req ca sub`

**Change sub name**

`cp /etc/easy-rsa/pki/issued/sub.crt`

**And that's it you can now create your on certificates**




