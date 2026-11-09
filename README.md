# Medieval Charters Knowledge Graph (MCKG)

[![Version Status](https://img.shields.io/badge/version-1.2.0-green.svg)](https://github.com/ExarcaFidalgo/MCKG-A-Community-Driven-Knowledge-Graph-on-Medieval-Charters)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-blue.svg)](https://creativecommons.org/licenses/by/4.0/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24079712.svg)](https://doi.org/10.5281/zenodo.24079712)

This repository contains all supplemental materials -including the datasets, code, and validation artefacts- supporting the paper:

**MCKG: A Community-Driven Knowledge Graph on Medieval Charters**

Published in the Semantic Web Journal. DOI: https://doi.org/10.1177/22104968261499445

The **Medieval Charters Knowledge Graph (MCKG)** is a provenance-aware knowledge graph constructed from the **AMSPO medieval charter corpus**, modeling persons, institutions, events, properties, and genealogical relations described in medieval Spanish charters.

The live Wikibase instance is publicly available at [Wikibase cloud](https://medievalcharterskg.wikibase.cloud/wiki/Main_Page).
RDF datasets (Turtle format) used to populate the MCKG are available in the `datasets/` directory and can be downloaded directly for reuse in external applications: [Attested Dataset](https://github.com/ExarcaFidalgo/MCKG-A-Community-Driven-Knowledge-Graph-on-Medieval-Charters/tree/master/datasets/Attested%20Dataset) and [Normalized Dataset](https://github.com/ExarcaFidalgo/MCKG-A-Community-Driven-Knowledge-Graph-on-Medieval-Charters/tree/master/datasets/Normalized%20Dataset).

The dataset is also available at [Zenodo](https://doi.org/10.5281/zenodo.24079712).

## Table of Contents

- [Corpus description](#corpus-description)
- [Knowledge Graph Scope](#knowledge-graph-scope)
- [Dataset Representations and Provenance](#dataset-representations-and-provenance)
- [Dataset Versioning, Licenses and Statistics](#dataset-versioning-licenses-and-statistics)
- [Reproducibility](#reproducibility)
- [Repository Structure](#repository-structure)
- [Intended audience](#intended-audience)
- [Contact](#contact)

## Corpus description
* **Source corpus**: AMSPO medieval charter corpus
* **Document type**: Medieval legal charters (e.g., donations, property transactions, institutional acts)
* **Geographical scope**: Asturias, Spain
* **Temporal coverage**: 14th century
* **Language**: Medieval Spanish

The corpus contains documentary records describing legal, economic, and social relationships between individuals and institutions.
Each document entity in the MCKG includes the archival identifier used in the AMSPO corpus (e.g., AMSPO, FSV, nº XXXX), enabling users to locate the corresponding charter in the scholarly transcription cited in the original paper _(Felpeto Cueva J. El archivo de un artesano del siglo XIV: el orfebre Alfonso Fernández de Oviedo. doctoral thesis, University of Oviedo, 2023. URL https://digibuo.uniovi.es/dspace/handle/10651/71402. Accepted: 2024-02-16T11:28:22Z.)_.

## Knowledge Graph Scope

The MCKG provides a structured semantic representation of documentary information extracted from medieval Spanish charters (AMSPO corpus). It models:
* Legal and socio-economic acts recorded in charters (e.g., donations, property transfers), including their temporal context and role-based participation of agents.
* Natural persons and institutions appearing in the documents.
* Explicit kinship and institutional affiliations asserted in the text.
* Properties involved in legal transactions and ownership transitions.
* Provenance distinguishing domain expert annotations from community-supported contributions.

The data model combines the event-centric semantics of [CIDOC-CRM](https://cidoc-crm.org/sites/default/files/Documents/cidoc_crm_version_7.1.3.html) with selected properties aligned to [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page), implemented within a Wikibase environment and validated through Shape Expressions (ShEx).

## Dataset Representations and Provenance

The MCKG provides two complementary representations of the AMSPO medieval charter corpus, distinguished by their treatment of historical names and documentary expressions:

- **Attested Dataset (expert-based and community-extended):** Built upon the original domain-expert annotations and subsequently expanded through community contributions supported by semi-automatic analysis. In the initial release, these additional contributions were provided by the authors. This dataset preserves the names and textual forms attested in the source documents. For example, a historical name recorded as *Iohan Periz* is represented as *Iohan Periz*, rather than being converted into its modernized equivalent. The dataset prioritizes fidelity to documentary expressions while organizing the extracted information according to the MCKG semantic model.

- **Normalized Dataset (domain-expert):** Derived from manual annotations by domain experts, this dataset applies historical-linguistic normalization to documentary expressions. For example, *Iohan Periz* may be represented as *Juan Pérez*. This representation supports research requiring normalized historical denominations and expert-mediated interpretation.

The main distinction between these datasets concerns their **representation objectives**. Both representations are grounded in domain-expert work. The Attested Dataset extends that foundation through additional contributions while preserving documentary forms, whereas the Normalized Dataset retains expert-normalized expressions.

The Attested Dataset is particularly suitable for evaluating document-grounded information extraction, where the objective is to recover entities and associated information as expressed in the source documents. The Normalized Dataset is more appropriate for tasks requiring historical-linguistic normalization.

The term *attested* refers to the preservation of documentary forms; it does not imply the absence of semantic classification or technical normalization of structured fields.

## Dataset Versioning, Licenses and Statistics

### Version
* **Current version**: v1.2.0
* **Release date**: 2025-05-13
* **Last update**: 2026-09-11

### Licenses
* **Dataset License**. The RDF datasets are released under _Creative Commons Attribution 4.0 International (CC BY 4.0)_
* **Code License**. The code in this repository is released under _MIT License_.

Users must comply with the respective license terms when reusing data or code.

### Statistics (v1.1.0)

* 2211 entities.
* 15542 statements.
* 7196 qualifying statements.
* 18810 reference statements.
* 128 documents processed.
  
### Version history

**v1.2.0 (current release)**
- Corrected erroneous annotations and resolved missing information in the Attested Dataset.
- Added previously omitted entities and associated documentary information to improve the completeness and accuracy of the dataset.
- Renamed the Community Dataset to Attested Dataset and the Domain Expert Dataset to Normalized Dataset to clarify their respective representation objectives.
- Updated the documentation to distinguish the preservation of historically attested names and textual forms from expert-mediated historical-linguistic normalization.

**v1.1.0**  
- Added `mentions entity` helper property to document entities to improve navigation between documents and referenced entities.  
- Added missing `is documented in` statements for some location entities.  
- Added explicit reference to the scholarly source representing the AMSPO corpus.  
- Expanded and clarified repository and Wiki documentation.  
- Expanded and reorganized SPARQL example queries.  
- Improved visibility of SPARQL queries and RDF/Turtle datasets.  
- Updated dataset statistics.

**v1.0.0**  
- Initial public release of the MCKG dataset.

## Reproducibility

This repository provides all artefacts required to:
* Inspect the RDF datasets derived from the AMSPO corpus.
* Reproduce the RDF-to-Wikibase ingestion workflow.
* Examine validation constraints (ShEx / EntitySchemas).
* Re-run SPARQL-based statistical analyses.

The RDF datasets provided here correspond to the data ingested into the public Wikibase instance (version v1.1.0). The live MCKG instance and the repository together ensure reproducibility of the population pipeline described in the paper. 

## Repository Structure
All resources are bundled in _mckg.zip_ and organized as follows:
* _datasets_ contains RDF datasets (Turtle format) produced by applying our pipeline to the AMSPO corpus:
	* Attested Dataset: RDF/Turtle files based on domain-expert annotations and expanded through community contributions supported by semi-automatic analysis. In the initial release, these contributions were made by the authors. The dataset preserves historical names and textual forms as attested in the source documents.
	* Normalized Dataset: RDF/Turtle files derived from manual domain-expert annotations, representing documentary information using expert-normalized historical expressions.
* _code_ contains Jupyter Notebooks implementing key pipeline components:
  * _CSVGenerator_ performs RDF-to-CSV conversion for Wikibase ingestion.
  * _Medieval NER with Roberta_ performs domain-specific NER to facilitate data extraction by community contributors.
  * _Shexer_ extracts Shape Expressions from the RDF datasets for validation and EntitySchema construction.
  * _WikibaseIntegration_ loads into the MCKG core entities and properties of the data model, as well as the processed datasets in CSV format.
* _csv_ contains the csv files used in _WikibaseIntegration_. Those with the nomenclature _wikibase_import_X_dataset_ are an output of CSVGenerator.
* _shapes_ stores both Shape Expressions extracted by _sheXer_ and the resulting EntitySchemas, available as well in the MCKG for validation.
* _sparql_ contains the SPARQL queries used for generating dataset statistics and for the analytical examples discussed in the paper. These queries are also available as executable examples in the MCKG Query Service.
  The queries are organized by research theme, including:
  * _Charter and transaction analysis_.
  * _External knowledge integration_.
  * _Genealogical reconstruction_.
  * _Linguistic and onomastic analysis_.
  * _Prosopographic and sociographic analysis_.
  * _Provenance-aware queries_.
  * _Spatial analysis_.
  * _Statistics_.
* _NER_ contains RoBERTa NER outputs, used as support for community contributions.

This README is included in both the ZIP file and repository root for clarity.

## Intended audience
The MCKG is intended for:
* Historians working with medieval charter corpora
* Digital humanities researchers
* Semantic Web researchers

## Contact

The MCKG was developed by [WESO research group](https://www.weso.es/).

Responsible researchers:
* **Jorge Álvarez-Fidalgo**, Universidad de Oviedo
* **Enrique Rodriguez-Martin**, Universidad de Oviedo
* **Jose Emilio Labra-Gayo**, Universidad de Oviedo

For inquiries, collaboration proposals, or technical issues, contact alvarezfjorge@uniovi.es or open an issue in this repository.

