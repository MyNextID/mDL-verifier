# MyNextID mDL Reader Product Profile

## OpenID4VP Profile

The MyNextID mDL Reader adheres to the OpenID for Verifiable Presentations
(OpenID4VP) profile, which defines a set of standards and protocols for
presenting and verifying verifiable presentations of identity credentials, such
as mobile driver's licenses (mDLs). This profile ensures interoperability and
compliance with industry standards for secure and reliable mDL verification.

The profile also supports the OpenID for Verifiable Credentials (OpenID4VC) API,
providing compatibility with the latest industry developments in verifiable
credentials.

## X509 Certificate Profile

The MyNextID mDL Reader utilizes an X.509 certificate profile for secure
communication and authentication. X.509 certificates are widely recognized for
their use in establishing trust and ensuring the integrity of data exchanged
between the mDL Reader and the mDL issuer. This certificate profile is designed
to enhance the security and reliability of mDL verification processes.

## ISO mDL Standards Adherence

The MyNextID mDL Reader adheres to the following ISO standards for mobile
driver's licenses:

- **ISO 18013-5**: This standard specifies the data structure and encoding of
mobile driver's licenses (mDLs) and their representation in a two-dimensional
barcode format. The MyNextID mDL Reader conforms to the ISO 18013-5 standard to
ensure consistency and compatibility.

- **ISO/IEC 18013-7 Version N7215**: This version of ISO/IEC 18013-7 is the
latest revision, and the MyNextID mDL Reader aligns with it to provide
up-to-date compliance with ISO standards.

## mDL Reader Verification Steps

The following table outlines the verification steps performed by the MyNextID
mDL Reader during the mDL verification process:

| Step Number | Verification Action                | Description                                                      |
|-------------|-----------------------------------|------------------------------------------------------------------|
| 1           | Connect to mDL                    | Establish a secure connection to the mDL for data retrieval.     |
| 2           | Decode / decrpyt mDL Data         | Decode or decrypt the data within the mDL to extract relevant information.   |
| 3           | Verify Digital Signature          | Verify the digital signature on the mDL to confirm its authenticity. |
| 4           | Check mDL Expiry                  | Ensure that the mDL has not expired and is valid for use.        |
| 5           | Verify Issuer Signature           | Verify the issuer's digital signature on the mDL data.           |
| 6           | Validate received data            | Check if the response includes all requested namespaces and data elements in the correct format, and no extraneous namespaces or elements. |
| 7           | Validate mDL Holder Data          | Check if mDL Holder data corresponds with signed issuer data.  |

These verification steps ensure that the MyNextID mDL Reader can reliably and
securely verify the authenticity and validity of mobile driver's licenses,
providing a trusted solution for identity verification.

For more detailed information on the MyNextID mDL Reader and its capabilities,
please refer to our comprehensive documentation.

---
© 2023 MyNextID. All Rights Reserved.
