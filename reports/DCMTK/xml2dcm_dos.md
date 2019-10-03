# DoS in xml2dcm utility

Memory corruption related crashes have been discovered during fuzz-testing of xml2dcm.

## Versions:
* DCMTK 3.6.2 (Linux x64)
* DCMTK 3.6.2 (MacOS x64)

The vendor was informed. The weakness has been [fixed](https://support.dcmtk.org/redmine/issues/896).