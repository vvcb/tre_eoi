# TECHNOLOGY AND DATA

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

## LSC

- Microsoft Azure

High level architecture:

- Landing Zone, AVD (VDI) environment, TRE environment
- [ ] Include high level architecture diagrams

Networking:

- Express Route connects Azure to On-Prem network
- All assets within Azure TRE are protected with private endpoints and accessed through peered private VNETs
- Azure Firewall and Bastion setup for vendor access

Authentication/Authorisation:

- Extensive use of Azure Active Directory and
- Based around principle of least privilige

Data Warehousing:

- Currently uses Azure Data Lake Storage V2 (with Azure Files, Blob, Storage Queues and Table storage)
- Proposal to use Azure Synapse / Snowflake

Analytical tooling:

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

Todo:

- [ ] High level architecture diagrams
- [ ] Differentiate between TRE and SDE
- [ ] Include AzureTRE architecture and our work so far
- [ ] OHDSI/OMOP
- [ ] OpenSAFELY proposal that was discussed with Ben Goldacre in July/August

```{note}
Outline your roadmap to meet the mandatory requirements for SDE accreditation. See (Appendix C) for full detail of requirements.
```
