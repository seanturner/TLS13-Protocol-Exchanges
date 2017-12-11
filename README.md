# TLS 1.3 Protocol Exchanges

## Introduction

This is just a collection of ASCII Art depicting possible protocol flows for TLS1.3 (insert reference).

There is no intent to turn this into an I-D.

## 1-RTT

### Nothing Fancy

    Client                                               Server
    
    ClientHello
    + supported_versions
    + key_share
    + supported_groups
    + signature_algorithms
    + server_name             -------->
                                                    ServerHello
                                                    + key_share
                                                   {Certificate}
                                             {CertificateVerify}
                              <--------               {Finished}
    {Finished}                -------->
    [Application Data]        <------->      [Application Data]
