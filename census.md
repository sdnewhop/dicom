# DICOM Internet Census

## Overview
The most popular and known DICOM solutions are enumerated using search engines.

## Vendors
- [PMOD Technologies](#pmod-technologies)
- [GE Healthcare](#ge-healthcare)
- [Orthanc](#orthanc)
- [Xinapse Systems](#xinapse-systems)
- [DICOM Grid](#dicom-grid) (Alse known as Ambra Health)

## Basic Search Queries
#### Shodan
* DICOM FINDSCU
* DICOM -FINDSCU
* "Content-Type: applicaiton/dicom"
* "DICOM Server Response"
* DICOM port:"104"
* DICOM port:"11112"
* port:"2761"
* port:"2762"

## PMOD Technologies
Confidence: Tentative  

### PMOD Dicom Server
#### Shodan
* port:"4000" DHT Nodes
* port:"4030" DHT Nodes

## GE Healthcare
Confidence: Tentative  

### NM General Purpose 600 Series
#### Shodan
* port:"4006"

## Orthanc
Confidence: Certain  

### Orthanc Server
#### Shodan
* title:"Orthanc Explorer"
* port:"4242"

## Xinapse Systems
Confidence: Tentative  

### DICOM Storage Server
#### Shodan
* port:"4560"

## DICOM Grid
Confidence: Tentative

### DICOM Grid Gateway
#### Shodan
* port:"4006"
* port:"8161"
