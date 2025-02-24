---
tags:
  - software_info
---
> ℹ Software Bill of Materials

# What is it
The Software Bill of Materials (short: __SBOM__) is a list of used dependencies within the project. It follows a formal and structured format and contains components of the software product and the relations within the software delivery chain. A SBOM is obligatory in the __USA__.

----

## How does the Syntax look like?
It needs to follow the  [guideline of NTIA](https://www.ntia.doc.gov/files/ntia/publications/sbom_minimum_elements_report.pdf):

- Name of the publisher
- Component name
- Version of the component
- Other unique identifiers (e.g. from the NIST CPE Dictionary)
- Dependency relations
- Author of the SBOM-Data
- Timestamp of the last modification of the SBOM data

Each entry has to comply further with:

- Follow one of three standardized formats ([SPDX](https://spdx.dev/), [CycloneDX](https://github.com/CycloneDX) or [SWID-Tags](https://csrc.nist.gov/projects/Software-Identification-SWID))
- Each new software version requires a new SBOM
- Must include not only know dependency relationships but also information where possible relations could exist but are unknown by the author

----

## Generate a SBOM
There are tools called [[SCA]] (Software Composition Analysis). They search through the dependencies for related libraries and create a Tree of libraries.

----
##### References
-  CSOonline.com: Was ist eine Software Bill of Materials, [link](https://www.csoonline.com/de/a/was-ist-eine-software-bill-of-materials,3674040)