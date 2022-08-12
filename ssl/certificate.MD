

## PFX certificate (for Azure)

### Getthe Private KEY

1. convert the jks to p12:
```shell
keytool -importkeystore -srckeystore pair.jks -destkeystore keystore.p12 -deststoretype PKCS12
```
2. get the private key from p12
```shell
openssl pkcs12 -in keystore.p12 -nocerts -nodes -out private.key
```

### Create PFX file: (required key & Cert)
```
openssl pkcs12 -export -out domain.name.com.pfx -inkey private.key -in domain_name_com.crt
```

![image](https://user-images.githubusercontent.com/9446035/184226126-dec3e9a6-589b-479a-af24-07177ae012d2.png)
