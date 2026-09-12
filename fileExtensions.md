Table of contents

1. [.Pem file](#.pem-file)
1. [.CSR file](#.csr-file)
1. [.KEY file](#.key-file)
1. [.p12 file](#.p12-file)
1. [.lic file](#.lic-file)
1. [.jks file](#.jks-file)

## .pem-file
A PEM (Privacy-Enhanced Mail) file is a text-based container file format used to store and transmit cryptographic data, such as SSL/TLS certificates, private keys, public keys, and certificate chains.

## .csr-file
This is a Certificate Signing Request. Some applications can generate these for submission to certificate-authorities. The actual format is PKCS10 which is defined in RFC 2986. It includes some/all of the key details of the requested certificate such as subject, organization, state, whatnot, as well as the public key of the certificate to get signed. These get signed by the CA and a certificate is returned. The returned certificate is the public certificate (which includes the public key but not the private key), which itself can be in a couple of formats.

## .key-file
This is a (usually) PEM formatted file containing just the private-key of a specific certificate and is merely a conventional name and not a standardized one. In Apache installs, this frequently resides in /etc/ssl/private. The rights on these files are very important, and some programs will refuse to load these certificates if they are set wrong. Technically, this is a base64 version of a PKCS8-formatted key (RFC 5958).

## .p12-file
Originally defined by RSA in the Public-Key Cryptography Standards (abbreviated PKCS), the "12" variant was originally enhanced by Microsoft, and later submitted as RFC 7292. This is a password-protected container format that contains both public and private certificate pairs. Java 9 and newer (2017 onwards) defaults to these files over the older proprietary .jks or PKCS files (see below). Unlike .pem files, this container is fully encrypted and has standard ways of encoding whole chains. Openssl can turn this into a .pem file with both public and private keys: openssl pkcs12 -in file-to-convert.p12 -out converted-file.pem -nodes

## .lic-file
A .lic file is a digital software license file used by programs, servers, and networks to verify that a user or system is authorized to run an application.

## .jks-file
A .jks file stands for Java KeyStore. It is a secure, password-encrypted container file format used by Java-based applications to store cryptographic keys and digital certificates.
