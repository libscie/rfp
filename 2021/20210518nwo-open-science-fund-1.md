# Automatic Detection of Identifiers in Open Data (ADIODA)

## Co-authors

* [Jelte Wicherts](https://orcid.org/0000-0003-2415-2933)
* Rick Klein

## English summary

Privacy breaches pose a major risk in the dissemination of rich datasets in the medical, social, and behavioural
sciences, particularly when the data involve sensitive information. Here, we develop and validate an open tool
called Automatic Detection of Identifiers in Open Data (ADIODA) allowing researchers in these fields to proactively
and readily identify information in datasets that could (inadvertently) be used to (re-)identify individuals. ADIODA
will be an open tool that can be easily implemented in research workflows, data audits, and editorial procedures
to help protect the privacy of participants whose information is used in openly shared datasets.

## Dutch summary

Privacy-schendingen vormen een groot risico bij het delen van rijke gegevensbestanden in de medische, sociale,
en gedragswetenschappen, vooral wanneer de gegevens gevoelige onderwerpen betreffen. We ontwikkelen en
valideren hier een open tool genaamd Automatic Detection of Identifiers in Open Data (ADIODA) waarmee
onderzoekers vooraf eenvoudig identificerende informatie kunnen detecteren waarmee anders individuen in de
gegevens hadden kunnen worden geïdentificeerd. ADIODA is een open tool die eenvoudig kan worden
geïmplementeerd in onderzoeksprojecten, gegevenscontroles, en redactionele procedures om de privacy te
helpen beschermen van deelnemers wiens gegevens in open databestanden voorkomen.

## Project vision

Researchers in the medical, social, and behavioural sciences increasingly share the data behind their scientific claims, with many benefits for society and science in terms of verification and re-use. Yet, when datasets contain sensitive information from human subjects, researchers need to be acutely aware of privacy risks of sharing data.

In a recent meta-research project funded by the European Research Council (Wicherts et al., in prep.), we assessed ~2,000 datasets published alongside articles in three popular psychology journals, where we observed direct privacy risks (e.g., names, birth-dates, IP addresses) in about 5% of those datasets. Of those, over half contained sensitive data according to Europe Union’s General Data Protection Regulation (GDPR). These ethical and legal violations of privacy pose risks to participants, researchers, and universities.

The many benefits of open data mean that the solution to these risks can’t be to reverse course and resume the outdated norm of closed data. With this grant, we hope to equip researchers with better safeguards to prevent privacy violations before they happen. Specifically, based on insights and data from our recent meta-research project, we aim to create and validate a tool called Automatic Detection of Identifiers in Open Data (ADIODA) that allows researchers to readily identify possibly identifying information in datasets before they are shared. This open-source tool can be easily integrated into workflows to check whether the data researchers are about to disseminate contains common types of identifiable information according to the GDPR (EU) or the Health Insurance Portability and Accountability Act (USA). The tool is not meant to replace existing (rather bureaucratic) legal and organizational efforts dealing with privacy, but rather to offer an extra check that can be readily implemented to proactively lower the risks of privacy breaches in open data.

ADIODA is an important tool for creating responsible open data. The target audience includes all researchers studying human subjects with quantitative data, including those who are still hesitant to share out of privacy concerns.

The intended outputs are

* dictionary of empirically evaluated regular expressions to detect common privacy risks
* an implementation of these regular expressions in an R package
* an implementation in an easy-to-use desktop application for researchers to install on their device (so potentially sensitive data does not need to be transmitted over the Internet).

We will implement a change management procedure to make researchers and editors of journals that include open data aware of this tool, such that we can work on bringing about social change. To this end, we will organize a virtual event to bring together researchers to discuss responsible data sharing.

This grant advances open science by working towards responsible data sharing, as a form of responsible research conduct.

## Project plan
### Step 1

Re-using the datasets identified and inspected in Wicherts et al. (in prep), as well as synthetic datasets that we will generate as additional training cases, we create and optimize a set of regular expressions that can detect potentially identifying information (e.g., IP addresses, birth dates, ZIP codes) in datasets. By using the cases from Wicherts et al. (in prep), we ensure broad coverage for common types of identifying information found in journals like Psychological Science, Judgement and Decision Making, and PLOS ONE. This will include making a list of the identifiable and sensitive information found in these datasets, distilling their prototypical forms into regular expressions, and scanning the data to empirically evaluate performance against the previously collected data.

### Step 2

Subsequently, we will go back to the GDPR and HIPAA legislation and the wider privacy literature to search for potential omissions or types of identifying information that were not present in the Wicherts et al. training set. We will tune the regular expressions to try to capture as many of the categories of personally identifying information as possible. At the same time, we will collect datasets to use as a validation sample to test the performance of the regular expressions outside the scope of the Wicherts et al. sample. We have two strategies for this: First, research assistants will use a protocol to scan datasets from common psychology journals for identifying information. Second, we will reach out to data repositories like Data Archiving Networked Services (DANS) and the Open Science Framework (with which we successfully collaborated in the past) to introduce the tool and seek to partner with them to identify additional datasets, privacy risks, and considerations that would improve performance of the tool. Upon completion of this validation, we will have a good estimate for how well the regular expressions perform.

### Step 3

After validating the regular expressions, we will implement them in an R package, using the most recent standards for R packages, and automated testing of the implementation, which evaluates the performance of the software upon each change to prevent reduced performance.

### Step 4

We implement the regular expressions into a customized desktop application, built using the framework Electron
and React. We will test the application with ten researchers in our network, to optimize ease-of-use. We will
implement an auto-update procedure to ensure users always have the latest version of the software. In the last
step, we will also a virtual event to help disseminate the new tool among potential users.
