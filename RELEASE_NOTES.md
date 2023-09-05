# Product Release Notes

- [Product Release Notes](#product-release-notes)
  - [Version 1.0.0 - Initial Release (June, 2023)](#version-100---initial-release-june-2023)
  - [Version 1.0.1 - Interop-event Updates (August, 2023)](#version-101---interop-event-updates-august-2023)
  - [Version 1.0.2 - Interop-event Updates (August, 2023)](#version-102---interop-event-updates-part-2-august-2023)
  - [Version 1.0.3 - Interop-event Updates (August, 2023)](#version-103---interop-event-updates-part-3-august-2023)
  - [Version 1.0.4 - Interop-event Updates (August, 2023)](#version-104---interop-event-updates-part-4-august-2023)

## Version 1.0.0 - Initial Release (June, 2023)

### Overview

We are thrilled to announce the initial release of the MyNextID mDL Reader, a
powerful and secure solution for mobile driver's license (mDL) verification.
This release marks a significant milestone in our commitment to providing
reliable identity verification tools.

### Key Features

- **Streamlined Verification**: Easily connect to and verify mDL data for quick and reliable identity checks.
- **OpenID4VP Profile**: Adheres to the OpenID for Verifiable Presentations (OpenID4VP) profile for industry-standard compatibility.
- **X.509 Certificate Profile**: Utilizes X.509 certificates for secure communication and data integrity.
- **ISO Standards Compliance**: Conforms to ISO 18013-5 and ISO/IEC 18013-7 Version N7215 for mDL standards compliance.

### Version Highlights

- **Secure and Reliable**: Our mDL Reader ensures the security and reliability of mDL verification processes.
- **User-Friendly Interface**: An intuitive user interface makes the verification process accessible to all users.
- **Documentation**: Comprehensive documentation is available to guide you through setup and integration.

## Version 1.0.1 - Interop-event Updates (August, 2023)

### New Features

- **OpenID4VC Support**: Added support for the OpenID for Verifiable Credentials (OpenID4VC) API, expanding compatibility with the latest industry standards in verifiable credentials.

### Enhancements

- **Improved Data Parsing**: Enhanced data parsing capabilities for more efficient decoding and extraction of mDL information.
- **User Interface Refinements**: Tweaked the user interface for a more intuitive and user-friendly experience.

### Bug Fixes

- **Signature Verification Fix**: Addressed an issue related to digital signature verification, ensuring the accuracy and security of mDL data.

## Version 1.0.2 - Interop-event Updates part 2 (August, 2023)

### Bug Fixes

- **JWE decryption fixed**: We have fixed an issue, with JWE decryption: go-jose/go-jose: error in cryptographic primitive
- **unknown Doctype**: in case of doctypes being present in issuerAuth, but not in nameSpaces used to throw an error, which should be normal and expected behaviour.
- **incorrect response_uri**: In some cases, users recieved an incorrect response_uri, this issue has been fixed.

## Version 1.0.3 - Interop-event Updates part 3 (August, 2023)

### New Features

- **Verifier Data and Security Check**: Added support for **V_DATA_3** Data and Security Check. Verifier now checks if `vp_token`, provided in AuthorizationResponseObject, includes all requested namespaces and data element identifiers. Verifier also checks if response doesn't contain extraneous namespaces or elements.

## Version 1.0.4 - Interop-event Updates part 4 (September, 2023)

### New Features

- **Issuer data authentication step**: Added step in issuer data authentication. Mdoc reader now validates  the certificate included in the MSO header. Certificate is validated using distributed X.509 IACA certificates provided by SprouseID.
- **mdoc Authentication Support**: Added support for mdoc authentication - **Security check V_SEC_3**. Mdoc reader now supports **mdoc ECDSA / EdDSA Authentication**. mdoc Reader verifies signature element in an **untagged COSE_Sign1** structure as defined in RFC 8152 and identified as `DeviceSignature`.

---

© 2023 MyNextID. All Rights Reserved.
