# Map-QBDT-E-24-Vendors-and-Customers-readmeVendor ID Format Overview 

This README provides foundational knowledge for understanding and working with vendor identifiers in the Capital Processing Systems Sandbox Middleware project. It is intended to help developers and analysts get started with vendor ID mapping and normalization logic. 

Background

We need to map entities in Sandbox Middleware Only Vendor Export 2025.10.26.xlsx to entities in Production Vendor Export 2025.10.31.  We only care about matching one way, meaning there are many more in Production than are on Sandbox. We can ignore them.

In the vendor export file Production Vendor Export 2025.10.31, each legal entity was randomly assigned a unique identifier by a human. There was no vetting to actual legal name.
In the vendor export file Sandbox Middleware Only Vendor Export 2025.10.26.xlsx, each legal entity is vetted and assigned a unique identifier. These identifiers follow two distinct formats: 

1. Cloud Based Admin System export of Payee Format 

Begins with a capital P followed by a 7-digit number. 

Ends with a space and the letter V. 

Example: P0000327 V, P0000359 V 

2. Cloud Based Admin System export of Seller Format 

Consists of a numeric ID without a prefix. 

Ends with a space and the letter V. 

Example: 10854 V, 10777 V 

Key Insight 

A single legal entity may have more than one unique vendor IDs—one in each format. This dual representation must be accounted for in any mapping, deduplication, or normalization logic. 

Project Implications 

Since in Production Vendor Export 2025.10.31 the first level unqiue identifier, and 2nd level entity name and address were created by humans without vetting, and the same records in Sandbox Middleware Only Vendor Export 2025.10.26.xls were vetted and created by program, matching will need to be fuzzy logic and look beyond just those fields.



 


 

For questions or contributions, please contact the project maintainer or submit an issue in the GitHub repository. 
