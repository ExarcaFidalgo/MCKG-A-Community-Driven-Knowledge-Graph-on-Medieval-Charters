# Medieval Charters Knowledge Graph (MCKG)

[![Version Status](https://img.shields.io/badge/version-1.0.0-green.svg)](https://github.com/ExarcaFidalgo/MCKG-A-Community-Driven-Knowledge-Graph-on-Medieval-Charters)
[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC_BY_4.0-blue.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

This repository contains all supplemental materials -including the datasets, code, and validation artefacts- supporting the paper:

**MCKG: A Community-Driven Knowledge Graph on Medieval Charters**

Submitted to the Semantic Web Journal.

The **Medieval Charters Knowledge Graph (MCKG)** is a provenance-aware knowledge graph constructed from the **AMSPO medieval charter corpus**, modeling persons, institutions, events, properties, and genealogical relations described in medieval Spanish charters.

The live Wikibase instance is publicly available at [Wikibase cloud](https://medievalcharterskg.wikibase.cloud/wiki/Main_Page).


## Table of Contents

- [Corpus description](#corpus-description)
- [Knowledge Graph Scope](#knowledge-graph-scope)
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
Each document entity in the MCKG includes the archival identifier used in the AMSPO corpus (e.g., AMSPO, FSV, nº XXXX), enabling users to locate the corresponding charter in the scholarly transcription cited in the original paper _(Felpeto Cueva J. El archivo de un artesano del siglo XIV: el orfebre Alfonso Fern´andez de Oviedo. doctoral thesis, University of Oviedo, 2023. URL https://digibuo.uniovi.es/dspace/handle/10651/71402. Accepted: 2024-02-16T11:28:22Z.)_.

## Knowledge Graph Scope

The MCKG provides a structured semantic representation of documentary information extracted from medieval Spanish charters (AMSPO corpus). It models:
* Legal and socio-economic acts recorded in charters (e.g., donations, property transfers), including their temporal context and role-based participation of agents.
* Natural persons and institutions appearing in the documents.
* Explicit kinship and institutional affiliations asserted in the text.
* Properties involved in legal transactions and ownership transitions.
* Provenance distinguishing domain expert annotations from community-supported contributions.

The data model combines the event-centric semantics of [CIDOC-CRM](https://cidoc-crm.org/sites/default/files/Documents/cidoc_crm_version_7.1.3.html) with selected properties aligned to [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page), implemented within a Wikibase environment and validated through Shape Expressions (ShEx).

## Dataset Versioning, Licenses and Statistics

### Version
* **Current version**: v1.0.0
* **Release date**: 2025-05-13
* **Last update**: 2025-05-13

### Licenses
* **Dataset License**. The RDF datasets are released under _Creative Commons Attribution 4.0 International (CC BY 4.0)_
* **Code License**. The code in this repository is released under _MIT License_.

Users must comply with the respective license terms when reusing data or code.

### Statistics (v1.0.0)

* 2211 entities.
* 12429 statements.
* 7117 qualifying statements.
* 12931 reference statements.
* 128 documents processed.

## Reproducibility

This repository provides all artefacts required to:
* Inspect the RDF datasets derived from the AMSPO corpus.
* Reproduce the RDF-to-Wikibase ingestion workflow.
* Examine validation constraints (ShEx / EntitySchemas).
* Re-run SPARQL-based statistical analyses.

The RDF datasets provided here correspond to the data ingested into the public Wikibase instance (version v1.0.0). The live MCKG instance and the repository together ensure reproducibility of the population pipeline described in the paper. 

## Repository Structure
All resources are bundled in _mckg.zip_ and organized as follows:
* _datasets_ contains RDF datasets produced by applying our pipeline to the AMSPO corpus:
  * _Community Dataset_ includes the RDF files generated from community contributions via semi-automatic analysis.
  * _Domain Expert Dataset_ includes the RDF files created from manual expert annotations.
* _code_ contains Jupyter Notebooks implementing key pipeline components:
  * _CSVGenerator_ performs RDF-to-CSV conversion for Wikibase ingestion.
  * _Medieval NER with Roberta_ performs domain-specific NER to facilitate data extraction by community contributors.
  * _Shexer_ extracts Shape Expressions from the RDF datasets for validation and EntitySchema construction.
  * _WikibaseIntegration_ loads into the MCKG core entities and properties of the data model, as well as the processed datasets in CSV format.
* _csv_ contains the csv files used in _WikibaseIntegration_. Those with the prefix _wikibase_import_dataset_ are an output of CSVGenerator.
* _shapes_ stores both Shape Expressions extracted by _sheXer_ and the resulting EntitySchemas, available as well in the MCKG for validation.
* _sparql_ includes all SPARQL queries used for generating statistics as well as the queries corresponding to the application examples. Those are also available as examples in the MCKG Query Service.
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

