# OpenLDAP Password Policy Implementation

## Purpose

This document describes implementation of password policy controls in OpenLDAP to improve authentication security and user account protection.

## Objectives

- Enforce minimum password standards.
- Support password expiry.
- Reduce unauthorized access risk.
- Improve account security.
- Support compliance with security requirements.

## Password Policy Features

The password policy may include:

- Minimum password length
- Password expiry
- Password history
- Account lockout
- Password change requirement
- Failed login control

## Enable Password Policy Overlay

Create a policy overlay LDIF file:

```ldif
dn: olcOverlay=ppolicy,olcDatabase={1}mdb,cn=config
objectClass: olcOverlayConfig
objectClass: olcPPolicyConfig
olcOverlay: ppolicy
olcPPolicyDefault: cn=default,ou=pwpolicies,dc=organization,dc=local
olcPPolicyHashCleartext: TRUE
