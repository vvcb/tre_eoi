# DATA ASSETS

## Todo

- [ ] Shorten this section. Move some of this to the _technology and data_ section
- [ ] Add links to OHDSI web resources
- [ ] Include CDM image

```{note}
What data assets do you intend to make available to researchers in your SDE for R&D? What data assets will be available by March 2025?  

A template is provided (Appendix F) for you to complete, should you wish.
```

## OHDSI/OMOP

Standardising multiple data sources into a single common data model has significant benefits that include easier data discovery, reproducible analysis and federated research using anonymised datasets.

LTH has used Quadramed (Harris Healthcare) as its primary electronic health record (EHR) for nearly 15 years.
This has resulted in a large amount of longitudinally collected patient data for over 2.2 million patients.
LTH also has multiple other application specific databases that continue to collect valuable data.

At present this data is stored in multiple data silos in non-standard data models and databases which makes large scale data analytics very difficult and often impossible.
This poses significant problems in getting value out of this data for the benefit of our patients through service improvement projects or research.
Moreover, we are unable to collaborate with other NHS organisations both within the ICS and the wider NHS without allocating significant resources to standardising data to a conformant format.

Data standardization is the critical process of bringing data into a common format that allows for collaborative, large-scale analytics, and sharing of sophisticated tools and methodologies.
The Observational Health Data Sciences and Informatics (or OHDSI, pronounced "Odyssey") program is a multi-stakeholder, interdisciplinary collaborative to bring out the value of health data through large-scale analytics.
The OMOP Common Data Model allows for the systematic analysis of disparate observational databases.

```{figure} ./images/omop_cdm54.png
---
width: 800px
name: omop-cdm
---
OMOP Common Data Model 5.4
```

The concept behind this approach is to transform data contained within those databases into a common format (data model) as well as a common representation (terminologies, vocabularies, coding schemes), and then perform systematic analyses using a library of standard analytic routines that have been written based on the common format.
Once a database has been converted to the OMOP CDM, evidence can be generated using standardized analytics tools.

OHDSI have developed Open-Source tools for data quality and characterization, medical product safety surveillance, comparative effectiveness, quality of care, and patient-level predictive modelling, but there are also other sources of such tools, some of them commercial.
