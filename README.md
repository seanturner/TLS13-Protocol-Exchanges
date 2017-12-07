# tls13 Protocol Exchanges

## Introduction

This is just a collection of ASCII Art depicting possible protocol flows for TLS1.3 (insert reference).

There is no intent to turn this into an I-D.

## 1-RTT

### 1-RTT Plain Jane

          Client                                               Server

    Key  ^ ClientHello
    Exch | + key_share*
         | + signature_algorithms*
         | + psk_key_exchange_modes*
         v + pre_shared_key*         -------->
                                                           ServerHello  ^ Key
                                                          + key_share*  | Exch
                                                     + pre_shared_key*  v
                                                 {EncryptedExtensions}  ^  Server
                                                 {CertificateRequest*}  v  Params
                                                        {Certificate*}  ^
                                                  {CertificateVerify*}  | Auth
                                                            {Finished}  v
                                     <--------     [Application Data*]
         ^ {Certificate*}
    Auth | {CertificateVerify*}
         v {Finished}                -------->
           [Application Data]        <------->      [Application Data]
