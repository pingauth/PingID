# PingID

* [Installation and Setup](#download-pingid-for-windows)
* [PingID Integration for Windows Login](#pingid-integration-for-windows-login)
* [PingID Integration for Mac Login](#pingid-integration-for-mac-login)
* [Mobile App (iOS & Android)](#mobile-app-ios--android)
* [Integration Kit for PingFederate](#integration-kit-for-pingfederate)

## Download PingID for Windows

**⬇️ [Download PingID Windows Installer](https://pingid-api.github.io/PingID)**

To install PingID, you need to download the appropriate integration package (Windows, macOS, or server platform). The setup process requires:

* The `pingid.properties` file (generated from the PingOne admin portal)
* Administrator rights
* Network access to PingID services
* GUI or CLI installers

> \[!note]
> For automated installation (e.g., using SCCM or MDM), make use of the CLI installer with options like `--silent` or `--very-silent`.

## PingID Integration for Windows Login

PingID for Windows improves login security for both local and RDP sessions.

### Key Features:

* MFA for initial login and screen unlocking
* Supports both password-based and passwordless login methods
* Offline authentication via paired devices or security keys
* Push authentication and number matching
* Support for FIDO2 keys (v2.3+)

> \[!tip]
> PingID for Windows is compatible only with machines acting as servers and validated Credential Providers (CP). Windows 10 does not support PIN.

```bash
pingid_install.exe --silent --rsa_padding
```

## PingID Integration for Mac Login

PingID for Mac enables MFA on macOS devices using either the GUI or CLI installer.

### Supported Features:

* MFA for login and lock screen
* OAEP padding for offline encryption
* Network selection available from the lock screen
* Language localization (Czech, Polish, Hungarian)
* Compatibility with macOS 10.15+ (Monterey and later)

> \[!warning]
> macOS versions 10.13 (High Sierra) and 10.14 (Mojave) are not supported.

## Mobile App (iOS & Android)

PingID provides dedicated mobile apps for both iOS and Android devices, offering:

* Push-based authentication
* Biometric login (Face ID, Touch ID)
* Offline OTP generation
* Apple Watch support

### App Versions:

* iOS: Latest version 1.8.4
* Android: Latest version 3.2.0

> \[!note]
> Offline functionality requires at least one successful pairing online.

## Integration Kit for PingFederate

PingID integrates with PingFederate using an SDK adapter.

### Steps:

1. Install the PingID SDK Integration Kit
2. Configure an adapter instance for PingID
3. Set up authentication policies and OpenID clients
4. Enable token management

> \[!info]
> Be sure to select the correct claim types (e.g., UPN vs. WindowsAccountName) during setup. This selection is **final** after configuration.

## PingID Desktop App

The desktop app serves as an alternative when mobile devices are unavailable or restricted.

### Key Functions:

* Local approval for authentication
* Secure offline token generation
* PIN-based control for desktop access

> \[!tip]
> Automatic updates and policy enforcement are available through admin settings.

## Passwordless Login Options

PingID supports several passwordless authentication methods:

* **Number matching** in the mobile app
* **FIDO2** security keys
* **Offline OTP** using soft tokens

> \[!warning]
> A 2-minute lockout occurs after 3 failed passwordless login attempts on Windows.

## SSH Integration

PingID can be set up to secure SSH access to Linux servers.

### Features:

* PAM module integration
* MFA prompts during SSH login
* TOTP, push, or FIDO2 authentication
* Command-line audit logs and fallback options

> \[!note]
> Setting up SSH integration may require root access and SSHD/PAM configuration.

## Release Notes & SDK Updates

PingID is actively developed, with detailed release notes available for each component:

* New CLI options: `--silent`, `--rsa_padding`
* Improved Monterey (macOS) support
* Push rate-limiting enhancements
* Updates for offline usage and FIPS compliance
* Security fixes (e.g., CVE-2022-23717 mitigation)

> \[!example]
> **PID-5297** – Resolved group-based login bypass vulnerability in Windows Login
