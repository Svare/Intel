## Encoding & Cipher Commands

```
man openssl | grep 'Encoding and Cipher Commands' -A 70
```

## ssh-keygen

```zsh
ssh-keygen -t rsa -b 1024 -N '123456' -f keypair.pem

ssh-keygen -o -a 100 -t ed25519 -N 'Hola123.,' -f ./id -C 'jinake'

```

## Get Public Key from Private Key

```
$ openssl rsa -in privkey -pubout

    writing RSA key
    -----BEGIN PUBLIC KEY-----
    MIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICCgKCAgEA5LQnENotwu/SUAshZ9va
    crnVeYXrYPJoxkaRc2Q3JpbRcZTuYxMJm2+5ZDzaDu5T4xLbcM0BshgOM8N3gMco
    gz0KUmMD3OGLt90vNBq8Wo/9cSyVRnBSnbCl0EzpFeeMBymR8aBm8sRpy7+n9VRa
    wmjX9os25CmBBJB93NnZj8QFJxPtu00f71w1pOL+CIEPAgSSZazwI5kfeU9wCvy0
    Q650ml6nC7lAbiinqQnocvCGbV0OaDFmO98dwdJ3wnMTkPAwvJcESa7iRFMSuelg
    st4xt4a1js1esTvvVHO/fQfHdYo35Y8r9yYeCarBYkFiqPMec8lhrfmviwcTMyK/
    TBRAkj9wKKXZmm8xyNcEzP5psRAMe4RO91xrgQx7ETcBuJm3xnfGxPWvqXjvbl72
    UNvU9ZXuw6zGaS7fxqf8Oi9u8R4rT/5ABWZ1CSucfIySfJJzCK/pUJzRNnjsEgTc
    0HHmyn0wwSuDp3w8EjLJIl4vWg1ZvSCEPzBJXnNqJvIGuWu3kHXONnTq/fHOjgs3
    cfo0i/eS/9PUMz4R3JO+kccIz4ZxNFvKwlJZH/4ldRNyvI32yqhfMUUKVsNGm+7C
    nJNHm8wG3CMS5Z5+ajIksgEZBW8SJosryuUVF3pShOIM+80p5JHdLhJOzsWMwap5
    7AWyBia6erE40DS0e0BrpdsCAwEAAQ==
    -----END PUBLIC KEY-----
```
