# X509-MDL-Reader Certificate Requirements Verification

- **Version of this document**: 1.0.0
- **Last Updated**: August 21, 2023
- **Conformant with Specification**: ISO/IEC 18013-5, Annex B.6

The mDL reader should use the following certificate profile for reader authentication.

## Requirement ID: X509-MDL-Reader-REQ-001
### Version
- **Mandatory**: Yes
- **Verification Step**: Ensure the certificate version is v3.

## Requirement ID: X509-MDL-Reader-REQ-002
### Serial Number
- **Mandatory**: Yes
- **Verification Step**: Verify that the serial number is a non-sequential positive integer containing at least 63 bits of output from a CSPRNG, and should contain at least 71 bits of output from a CSPRNG, with a maximum of 20 octets.

## Requirement ID: X509-MDL-Reader-REQ-003
### Signature
- **Mandatory**: Yes
- **Verification Step**: Confirm that the signature value matches the specified signature algorithm.

## Requirement ID: X509-MDL-Reader-REQ-004
### Issuer
- **Mandatory**: Yes
- **Verification Step**: Ensure that the issuer's binary value is the same as the subject of a CA certificate used for mdoc authentication.

## Requirement ID: X509-MDL-Reader-REQ-005
### Validity
- **Mandatory**: Yes
- **Verification Step**: 
  - Verify that the certificate has a validity period.
  - Ensure that the 'notBefore' date represents the date on which the certificate validity period begins.
  - Confirm that the 'notAfter' date is a maximum of 1187 days after the 'notBefore' date.

## Requirement ID: X509-MDL-Reader-REQ-006
### Subject
- **Mandatory**: Yes
- **Verification Step**: 
  - Confirm that the 'commonName' is present.

## Requirement ID: X509-MDL-Reader-REQ-007
### Subject Public Key Info
- **Mandatory**: Yes
- **Verification Step**: 
  - Ensure that the algorithm is set to 1.2.840.10045.2.1.
  - Confirm that the parameters are present and marked as critical.
  - Implicitly specify curve parameters through an OID associated with one of the specified curves.

## Requirement ID: X509-MDL-Reader-REQ-008a
### V3 Extensions - Authority Key Identifier
- **Mandatory**: Yes
- **Critical**: No
- **Verification Step**: Ensure that the key identifier matches the subject key identifier of the issuer CA certificate.

## Requirement ID: X509-MDL-Reader-REQ-008b
### V3 Extensions - Subject Key Identifier
- **Mandatory**: Yes
- **Critical**: No
- **Verification Step**: Verify that the 'subjectKeyIdentifier' is a SHA-1 hash of the subject public key BIT STRING value.

## Requirement ID: X509-MDL-Reader-REQ-008c
### V3 Extensions - Key Usage
- **Mandatory**: Yes
- **Critical**: Yes
- **Verification Step**: Confirm that the 'keyUsage' is marked as critical and contains Digital Signature.

## Requirement ID: X509-MDL-Reader-REQ-008d
### V3 Extensions - Subject Alternative Name
- **Optional**: Yes
- **Critical**: No

## Requirement ID: X509-MDL-Reader-REQ-008e
### V3 Extensions - Issuer Alternative Name
- **Conditional**: Yes
- **Critical**: No
- **Verification Step**: Must be present if present in the CA certificate. The value must match the issuer CA certificate alternative name.

## Requirement ID: X509-MDL-Reader-REQ-008f
### V3 Extensions - Key Extended Usage
- **Mandatory**: Yes
- **Critical**: Yes
- **Verification Step**: Confirm that the 'keyUsage' is set to 1.0.18013.5.1.6.

## Requirement ID: X509-MDL-Reader-REQ-008g
### V3 Extensions - CRL Distribution Point
- **Mandatory**: Yes
- **Critical**: No
- **Verification Step**: Ensure that the CRL distribution point is specified as a URI.

## Requirement ID: X509-MDL-Reader-REQ-008h
### V3 Extensions - Signature Algorithm
- **Mandatory**: Yes
- **Verification Step**: Confirm that the signature algorithm is one of the following: 1.2.840.10045.4.3.2, 1.2.840.10045.4.3.3, 1.2.840.10045.4.3.4.

---