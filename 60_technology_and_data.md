# TECHNOLOGY AND DATA

Todo:

- [ ] High level architecture diagrams
- [ ] Differentiate between TRE and SDE
- [ ] Include AzureTRE architecture and our work so far
- [ ] Include ICS BI Datawarehouse details (BedRock) here - and in data assets section next
- [x] OHDSI/OMOP
  - [ ] Add section on how this benefits federation and our region
- [ ] OpenSAFELY proposal that was discussed with Ben Goldacre in July/August

```{note}
Provide information about your SDE for R&D design and the technologies you intend to use.

This should include:
- Technical architecture  
- Infrastructure and data warehousing
- Data processing and curation
- Analytical tooling
- Privacy Enhancing Technologies
- Data discoverability
```

Lancashire Teaching Hospitals NHS Trust has built a cloud-first, scalable, secure, trusted research environment (TRE) on Microsoft Azure which will enable research, academic and commercial collaboration and support the move to early intervention and prevention.

The TRE architecture is scalable across the ICS and will ensure interoperability to allow federated access and collaboration between teams in different care settings, academia and industry partners across the region, and globally.

LTHTR is also a member of the Health Data Research UK Alliance further demonstrating our commitment to open, collaborative, big-data research for population health.

## Core functions

Highly secure and robust technical architecture AND processes to ensure compliance with 5-safes

### SAFE SETTINGS

- Secure, customisable, scalable, collaborative, cost-effective environments for advanced data analytics

### SAFE PROJECTS

- TRE DARS + Existing processes (eg. REC)

### SAFE PEOPLE

- Researcher training, accreditation; Identity management; User access lifecycle management

### SAFE DATA

- Data/Metadata catalogues to empower self-discovery of data assets for research.
- Common data models for federated research
- Privacy preserving architectures such as OpenSAFELY
- Pseudonymisation/anonymisation depending on use cases

### SAFE OUTPUTS

- SDC, ML model lifecycle management, explainability tools,
- Interoperability with other visualisation / decision support tools
- NEXUS Intelligence (Population Health Management Platform)
- Aristotle (MLCSU's visualisation platform to support commissioning)
- CIPHA Population Health platform
- Business Intelligence
- Risk stratification / clinical decision support

## Technical Architecture

- Microsoft Azure
- Landing Zone, AVD (VDI) environment, TRE environment
- [ ] Include high level architecture diagrams

### Networking

- Express Route connects Azure to On-Prem network
- All assets within Azure TRE are protected with private endpoints and accessed through peered private VNETs
- Azure Firewall and Bastion setup for vendor access

### Authentication/Authorisation

- Extensive use of Azure Active Directory and
- Based around principle of least privilige

## Data Warehousing

- Currently uses Azure Data Lake Storage V2 (with Azure Files, Blob, Storage Queues and Table storage)
- Proposal to use Azure Synapse / Snowflake

## Analytical tooling

- JupyterHub on Azure Kubernetes Service
  - Language support: Python, R, Julia, Octave
  - Interface support: JupyterLab, Jupyter Notebooks, RStudio Server
- Azure Virtual Desktop
  - Custom built Windows 10 Desktop Enterprise Data Science Image
  - Language support: Python, R (and possibly any other as required)
  - IDE support: VSCode, Jupyter, RStudio
  - Database tools: SQL Server Managament Studio, DBeaver, DBBrowser
  - Statistical software: JASP
  - Productivity tools: Office 365

### OHDSI Analytics Stack

__[OHDSI (Observational Health Data Sciences and Informatics)](https://www.ohdsi.org/)__ is multi-stakeholder, interdisciplinary collaborative to derive value out of health data through large-scale analytics using open-source tools

The __[OMOP - Common Data Model](https://www.ohdsi.org/data-standardization/)__ allows for the systematic analysis of disparate observational databases by transforming data contained within those databases into a common format (data model).
This allows for federated analyses of multiple such databases held at different sites using standard analytic routines without the need to share the underlying data.

The OHDSI network have also created __[Athena](https://athena.ohdsi.org/)__, a searchable repository of harmonised standard vocabularies.
This is used to map source data to internationally recognised ontologies such as SNOMED, ICD10, LOINC or other ontology of choice, making it interoperable with other similarly mapped data

Once source data has been converted into the OMOP model, this can be subject to exploration and advanced analytics using a large ecosystem of [open-source tools](https://www.ohdsi.org/software-tools/).

__[ATLAS](https://github.com/OHDSI/Atlas)__ is an open source software tool for researchers to conduct scientific analyses on standardized observational data converted to the OMOP Common Data Model V5.
Researchers can create cohorts by defining groups of people based on an exposure to a drug or diagnosis of a particular condition using healthcare claims data.
ATLAS has vocabulary searching of medical concepts to identify people with specific conditions, drug exposures etc.
Patient profiles can be viewed within a specific cohort allowing visualization of a particular subject's health care records.
Population effect level estimation analyses allows for comparison of two different cohorts and leverages R packages.

ATLAS by design does not reveal patient identifiable information and the built-in privacy preserving features of the OHDSI stack can be enhanced by following further steps during the data transformation process as described here <https://ohdsi.github.io/CommonDataModel/cdmPrivacy.html>.

```{figure} ./images/omop_atlas.png
---
width: 800px
name: omop-atlas
---
OHDSI ATLAS Web Interface
```

__[HADES](https://ohdsi.github.io/Hades/)__ is a set of open source R packages for large scale analytics, including population characterization, population-level causal effect estimation, and patient-level prediction.

__OHDSI International Community__

Global collaborators: <https://www.ohdsi.org/who-we-are/collaborators/>
UK Partners: <https://www.ehden.eu/datapartners/>

```{note}
Outline your roadmap to meet the mandatory requirements for SDE accreditation. See (Appendix C) for full detail of requirements.
```

In very simple terms, LSC intend to work with Microsoft to further co-develop the open source AzureTRE (<https://microsoft.github.io/AzureTRE/>) architecture. _Include details of Azure TRE here._

Map some of this to Appedix C (SDE specifications):

- Metadata catalogue and self-discovery, eg. <https://github.com/amundsen-io/amundsen> or Azure Purview
- Data governance and data lifecycle managememt - Azure Purview
- Workspace level data governance - eg. Azure ML workspace capabilities
- Tools for anonymisation/pseudonymisation eg. <https://amnesia.openaire.eu/>
