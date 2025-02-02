[Back to Main README](../README.md)


## Data Security

### Security Architecture

- **Local Data Encryption:**  
    All sensitive data stored on local devices is encrypted using SQLCipher, protecting data at rest even if the device is compromised.

- **Data Anonymization:**  
    Prior to transmission, data is processed to remove personally identifiable information (PII), ensuring privacy.

- **Secure Communication:**  
    Data is transmitted over HTTPS using robust encryption (TLS), safeguarding data in transit.

- **Cloud-Side Security:**  
    The Django backend enforces strong authentication, authorization, and audit logging. Regular security updates and penetration tests will be performed.

- **Compliance Focus:**  
    Every element of the system is designed with GDPR compliance in mind, and comprehensive documentation of data handling practices will be maintained.

---
[Back to Main README](../README.md)
