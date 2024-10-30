---
puppeteer:
    pdf:
        format: A4
        displayHeaderFooter: true
        landscape: false
        scale: 0.8
        margin:
            top: 1.2cm
            right: 1cm
            bottom: 1cm
            left: 1cm
    image:
        quality: 100
        fullPage: false
---

iOS WalletAPIError
==

- Topic: WalletAPIError
- Author: Dongjun Park
- Date: 2024-10-18
- Version: v1.0.0

| Version          | Date       | Changes                  |
| ---------------- | ---------- | ------------------------ |
| v1.0.0  | 2024-10-18 | Initial version          |

<div style="page-break-after: always;"></div>

# Table of Contents


- [iOS WalletAPIError](#ios-walletapierror)
- [Table of Contents](#table-of-contents)
  - [WalletAPIError](#walletapierror)
    - [Description](#description)
    - [Declaration](#declaration)
    - [Property](#property)
- [Error Code](#error-code)
  - [1. Common](#1-common)
  - [2. Token](#2-token)
  - [3. Lock](#3-lock)
  - [4. DB](#4-db)
  - [5. Wallet](#5-wallet)
  - [6. DID](#6-did)
  - [7. VC](#7-vc)
  - [8. VP](#8-vp)


## WalletAPIError

### Description
```
Error struct for Wallet API. It has code and message pair.
Code starts with MSDKWLT.
```

### Declaration
```swift
public struct WalletSDKError: Error {
    public var code: String
    public var message: String
}
```

### Property

| Name               | Type       | Description                            | **M/O** | **Note**              |
|--------------------|------------|----------------------------------------|---------|-----------------------|
| code               | String     | Error code    |    M    |                       | 
| message            | String     | Error description                      |    M    |                       | 

<br>

# Error Code

## 1. Common

| Error Code   | Error Message                        | Description                       | Action Required                    |
|--------------|--------------------------------------|-----------------------------------|------------------------------------|
| MSDKWLT05000 | Unknown error                        | Unknown error                     | Investigate the cause of the error |
| MSDKWLT05001 | General failure                      | General failure                   | Check for failure details          |
| MSDKWLT05002 | Failed to verify parameter           | Parameter verification failed     | Verify and correct parameters      |
| MSDKWLT05003 | Failed to serialize                  | Serialization process failed      | Check serialization process        |
| MSDKWLT05004 | Failed to deserialize                | Deserialization process failed    | Check deserialization process      |
| MSDKWLT05005 | Failed to create proof               | Proof creation failed             | Check proof creation logic         |
| MSDKWLT05006 | Failed to match role                 | Role matching failed              | Check the roles specified in certVC|
| MSDKWLT05007 | Failed to verify certVC              | certVC verification failed        | Check certVC verification logic    |

<br>

## 2. Token

| Error Code   | Error Message                        | Description                       | Action Required                   |
|--------------|--------------------------------------|-----------------------------------|-----------------------------------|
| MSDKWLT05010 | Failed to verify token               | Token verification failed         | Verify token and its validity     |
| MSDKWLT05011 | Failed to create wallet token        | Wallet token creation failed      | Check wallet token creation logic |

<br>

## 3. Lock

| Error Code   | Error Message                        | Description                       | Action Required                   |
|--------------|--------------------------------------|-----------------------------------|-----------------------------------|
| MSDKWLT05020 | Wallet is locked                     | Wallet access is restricted       | Unlock the wallet                 |

<br>

## 4. DB

| Error Code   | Error Message                        | Description                       | Action Required                   |
|--------------|--------------------------------------|-----------------------------------|-----------------------------------|
| MSDKWLT05030 | Failed to execute insert query       | Insert query execution failed     | Review query execution            |
| MSDKWLT05031 | Failed to execute select query       | Select query execution failed     | Review query execution            |
| MSDKWLT05032 | Failed to execute delete query       | Delete query execution failed     | Review query execution            |

<br>

## 5. Wallet

| Error Code   | Error Message                        | Description                       | Action Required                   |
|--------------|--------------------------------------|-----------------------------------|-----------------------------------|
| MSDKWLT05040 | Failed to create wallet              | Wallet creation failed            | Check wallet creation steps       |
| MSDKWLT05041 | Personalization failed               | Personalization failed            | Review personalization process    |
| MSDKWLT05042 | Depersonalization failed             | Depersonalization failed          | Review depersonalization process  |
| MSDKWLT05043 | Failed to save keychain              | Keychain saving failed            | Ensure proper keychain saving process |
| MSDKWLT05044 | Incorrect passcode                   | Passcode entered is incorrect     | Verify and re-enter the correct passcode |
| MSDKWLT05045 | Wallet ID not found                  | Specified wallet ID not found     | Check wallet ID                  |

<br>

## 6. DID

| Error Code   | Error Message                        | Description                       | Action Required                   |
|--------------|--------------------------------------|-----------------------------------|-----------------------------------|
| MSDKWLT05050 | Failed to register user              | User registration failed          | Check user registration process   |
| MSDKWLT05051 | Failed to restore user               | User restoration failed           | Check user restoration process    |
| MSDKWLT05052 | Failed to match DID                  | DID matching failed               | Check the DID to compare          |

<br>

## 7. VC

| Error Code   | Error Message                        | Description                       | Action Required                     |
|--------------|--------------------------------------|-----------------------------------|-------------------------------------|
| MSDKWLT05060 | Failed to issue credential           | Credential issuance failed        | Check credential issuance process   |
| MSDKWLT05061 | Failed to revoke credential          | Credential revocation failed      | Check credential revocation process |
<br>

## 8. VP
| Error Code   | Error Message                        | Description                       | Action Required                   |
|--------------|--------------------------------------|-----------------------------------|-----------------------------------|
| MSDKWLS05070 | submitCredentialFail                 | submit credential fail            | Check credential submit process   |