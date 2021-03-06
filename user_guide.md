GitHub: https://github.com/biocompute-objects
	
OSF page: https://osf.io/h59uh/ 

BioCompute Partnership: https://biocomputeobject.org

# BioCompute Object (BCO) User Guide

* This version: [draft](https://github.com/biocompute-objects/BCO_Specification/tree/master)
* Previous version: [v1.2.0](https://github.com/biocompute-objects/BCO_Specification/releases/tag/v1.2)
* Latest release: https://github.com/biocompute-objects/BCO_Specification/releases/latest
* Latest editor's draft: https://github.com/biocompute-objects/BCO_Specification/tree/master
<!-- FIXME: Ideally permalinks for all of the above links, say registering https://w3id.org/bco/ -->


This document was created by the [BioCompute Object Consortium members (BCOC)](#biocompute-object-consortium-members-bcoc)

### BCO_Specification is licensed under the [BSD 3-Clause "New" or "Revised" License](./LICENSE)

>A permissive license similar to the BSD 2-Clause License, but with a 3rd clause that prohibits others from using the name of the project or its contributors to promote derived products without written consent.

# 1 Introduction

This document specifies the structure of BioCompute Objects. 
The specification is split into multiple parts linked to from this 
top-level document and are maintained in a 
[GithHub repository](https://github.com/biocompute-objects/BCO_Specification)
where [contributions](README.md#support-community-and-contributing) are welcome.

Read more:

* [Introduction to BioCompute Objects](introduction.md)

# 2 BioCompute Domains

BCOs are represented in JSON (JavaScript Object Notation) formatted text, adhearing to [JSON schema draft-07](https://json-schema.org/specification.html). The JSON format was chosen because it is both human and machine readable/writable. For a detailed description of JSON see [www.json.org](http://www.json.org).

BioCompute data types are defined as aggregates of the critical fields organized into the following domains: the provenance domain, the usability domain, the extension domain, the description domain, the execution domain, the parametric domain, the input and output domains, and the error domain. At the time of creation with actual values compliant to the schema the BCO should be assigned a unique identifier, a [`bco_id`](/top-level.md#202-biocompute-object-identifier-bco_id). The object could then be assigned a unique digital [`checksum`](/top-level.md#203-checksum-checksum).

Three of the domains in a BioCompute Object SHOULD become immutable upon assignment of the digital `checksum`: 
1) the Parametric Domain
2) the Execution Domain and 
3) the I/O Domain

* [BCO domains](bco-domains.md)

# 3 Appendices

## 3.1 Appendix-I: BCO expanded view example

Complete example:

* [HCV1a.json](HCV1a.json)

## 3.2 Appendix-II: External reference database list

CURIEs (short identifiers) like `[taxonomy:31646]` in BCOs can be expanded to complete identifiers.

Specifications:

* [External references](external-references.md)

## 3.3 Title 21 CFR Part 11

*Code of Federal Regulations Title 21 Part 11: Electronic Records - Electronic Signatures*

BioCompute project is being developed with Title 21 CFR Part 11 compliance in mind. The digital signatures incorporated into the format will provide the basis for provenance of BioCompute Object integrity using NIST proposed encryption algorithms. Execution domain and parametric domain (that have a potential impact on a result of computation) and identity domain will be used to create hash values and digital signature encryption keys which later can be used for computer or human validation of transmitted objects. 

Discussions are now taking place to consider relevance of BioCompute Objects with relation to Title 21 CFR part 11. We encourage continuous input from BioCompute stakeholders on this subject now and while the concept is becoming more mature and more widely accepted by scientific and regulatory communities.

Relevant document link:

[Part 11: Electronic Records](http://www.fda.gov/RegulatoryInformation/Guidances/ucm125067.htm)

## 3.4 Appendix IV - Compatibility

### 3.4.1 ISA for the experimental metadata

ISA is a metadata framework to manage an increasingly diverse set of life science, environmental and biomedical experiments that employ one or a combination of technologies. Built around the **Investigation** (the project context), **Study** (a unit of research) and **Assay** (analytical measurements) concepts, ISA helps to provide rich descriptions of experimental metadata (i.e. sample characteristics, technology and measurement types, sample-to-data relationships) so that the resulting data and discoveries are reproducible and reusable. The ISA Model and Serialization Specifications define an Abstract Model of the metadata framework that has been implemented in two format specifications, ISA-Tab and ISA-JSON ([http://isa-tools.org/format/specification](http://isa-tools.org/format/specification)), both of which have supporting tools and services associated with them, including by a programmable Python AP ([http://isa-tools.org](http://isa-tools.org/format/specification)) and a varied user community and contributors ([http://www.isacommons.org](http://www.isacommons.org)). ISA focuses on structuring experimental metadata; raw and derived data files, codes, workflows etc are considered as external file that are referenced. An example, along its complementarity with other models and a computational workflow is illustrated in this paper, which shows how to explicitly declare elements of experimental design, variables, and findings: [http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0127612](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0127612) 

## 3.5 Appendix VI Acknowledgements

This document began development during the [2017 HTS-CSRS workshop](https://hive.biochemistry.gwu.edu/htscsrs/workshop_2017). The discussion during the workshop led to the refinement and completion of this document. The workshop participants were a major part of the initial BCO community, and the comments and suggestions collected during the sessions were incorporated into this document. The people who participated in the 2017 workshop, and therefore made significant contributions are listed here: [https://osf.io/h59uh/](https://osf.io/h59uh/)

### BioCompute Object Consortium members (BCOC)

**FDA:** Vahan Simonyan, Mark Walderhaug, Ruth Bandler, Eric Donaldson, Elaine Thompson, Alin Voskanian, Anton Golikov, Konstantinos Karagiannis, Elaine Johanson, Adrian Myers, Errol Strain, Khaled Bouri, Tong Weida, Wenming Xiao, Md Shamsuzzaman

**GW:** Raja Mazumder, Charles Hadley S. King IV, Amanda Bell, Jeet Vora, Krista M. Smith, Robel
Kahsay

**Documentation Community:** Gil Alterovitz (Boston Children’s Hospital/Harvard Medical School, SMART/FHIR/HL7, GA4GH), Michael R. Crusoe (CWL), Marco Schito (C-Path), Konstantinos
Krampis (CUNY), Alexander (Sasha) Wait Zaranek (Curoverse), John Quackenbush (DFCI/Harvard), Geet Duggal (DNAnexus), Singer Ma (DNAnexus), Yuching Lai (DDL), Warren Kibbe (Duke), Tony, Burdett (EBI), Helen Parkinson (EBI), Stuart Young (Engility Corp), Anupama Joshi (Epinomics), Vineeta Agarwala (Flatiron Health), James Hirmas (GenomeNext), David Steinberg (UCSC), Veronica Miller (HIV Forum), Dan Taylor (Internet 2), Paul Duncan (Merck), Jianchao Yao (Merck & Co., Inc., Boston, MA USA), Marilyn Matz (Paradigm4), Ben Busby (NCBI), Eugene Yaschenko (NCBI), Zhining Wang (NCI), Hsinyi (Steve) Tsang (NCI), Durga Addepalli (NCI/Attain), Heidi Sofia (NIH), Scott Jackson (NIST), Paul Walsh (NSilico Life Science), Toby Bloom (NYGC), Hiroki Morizono (CNMC), Jeremy Goecks (Oregon Health and Science University), Srikanth Gottipati (Otsuka-US), Alex Poliakov (Paradigm4), Keith Nangle (Pistoia Alliance), Jonas S Almeida (Stony Brook Univ, SUNY), Dennis A. Dean, II (Seven Bridges Genomics), Dustin Holloway (Seven Bridges Genomics), Nisha Agarwal (Solvuu), Stian Soiland-Reyes (UNIMAN), Carole Goble (UNIMAN), Susanna-Assunta Sansone (University of Oxford), Philippe Rocca-Serra (University of Oxford), Phil Bourne (Univ. of Virginia), Joseph Nooraga (Fred Hutchinson Cancer Research Center)

------

Contact: Raja Mazumder (mazumder@gwu.edu) and Vahan Simonyan (vahansim@gmail.com)
