# X509-Root-CA Certificate Requirements Verification

- **Version of this document**: 1.0.0
- **Last Updated**: August 21, 2023
- **Conformant with Specification**: ISO/IEC 18013-5, Annex B.1

This certificate profile defines the IACA root certificate, establishing the allowed security parameters for interoperability. The IACA root certificate is used as the root for all certificates.

## Requirement ID: X509-Root-CA-REQ-001
### Version
- **Mandatory**: Yes
- **Verification Step**: Ensure the certificate version is v3.

## Requirement ID: X509-Root-CA-REQ-002
### Serial Number
- **Mandatory**: Yes
- **Verification Step**: Verify that the serial number is a non-sequential positive integer containing at least 63 bits of output from a CSPRNG, and should contain at least 71 bits of output from a CSPRNG, with a maximum of 20 octets.

## Requirement ID: X509-Root-CA-REQ-003
### Signature
- **Mandatory**: Yes
- **Verification Step**: Confirm that the signature value matches the OID in the signature algorithm.

## Requirement ID: X509-Root-CA-REQ-004
### Issuer
- **Mandatory**: Yes
- **Verification Step**: 
  - Ensure that the 'countryName' is mandatory and contains the ISO 3166-1 alpha-2 code of the issuing country in upper case, exactly the same as in the issuing country data element.
  - Ensure that 'stateOrProvinceName' is mandatory and is in upper case, containing the ISO 3166-1 alpha-2 code.

## Requirement ID: X509-Root-CA-REQ-005
### Validity
- **Mandatory**: Yes
- **Verification Step**: 
  - Verify that the certificate has a validity period.
  - Ensure that the 'notBefore' date represents the date on which the certificate validity period begins.
  - Confirm that the 'notAfter' date is a maximum of 20 years after the 'notBefore' date. 
  - *Note*: The 20-year validity period results from the possibility of using the IACA root certificate for issuing an IDL according to ISO/IEC 18013-3, which allows the use of DS certificates with validity periods up to 15 years. If the IACA root certificate is only used to issue mDLs, a maximum validity period of 9 years is sufficient.

## Requirement ID: X509-Root-CA-REQ-006
### Subject
- **Mandatory**: Yes
- **Verification Step**: Ensure that the 'subject' has the same exact binary value as the 'issuer'.

## Requirement ID: X509-Root-CA-REQ-007
### Subject Public Key Info
- **Mandatory**: Yes
- **Verification Step**: 
  - Ensure that the algorithm is set to 1.2.840.10045.2.1.
  - Confirm that the parameters are present.
  - Verify that the 'subjectPublicKey' is in an uncompressed form.

## Requirement ID: X509-Root-CA-REQ-008a
### V3 Extensions - Subject Key Identifier
- **Mandatory**: Yes
- **Verification Step**: 
  - Ensure that the 'subjectKeyIdentifier' is present and non-critical.
  - Verify that it is a SHA-1 hash of the subject public key BIT STRING value (excluding tag, length, and number of unused bits).

## Requirement ID: X509-Root-CA-REQ-008b
### V3 Extensions - Key Usage
- **Mandatory**: Yes
- **Critical**: Yes
- **Verification Step**: 
  - Confirm that the 'keyUsage' extension is marked as critical.
  - Ensure that it contains 'Key certificate signature' and 'CRL signature'.

## Requirement ID: X509-Root-CA-REQ-008c
### V3 Extensions - Issuer Alternative Name
- **Mandatory**: Yes
- **Verification Step**: 
  - Ensure that the 'issuerAltName' extension is present and non-critical.
  - Verify that it includes a URI.

## Requirement ID: X509-Root-CA-REQ-008d
### V3 Extensions - Basic Constraints
- **Mandatory**: Yes
- **Critical**: Yes
- **Verification Step**: 
  - Confirm that the 'basicConstraints' extension is marked as critical.
  - Ensure that it has 'CA' set to TRUE and 'pathLenConstraint' set to 0.

## Requirement ID: X509-Root-CA-REQ-008e
### V3 Extensions - CRL Distribution Points
- **Mandatory**: Yes
- **Critical**: No
- **Verification Step**: 
  - Ensure that the 'cRLDistributionPoints' extension is present and non-critical.
  -
