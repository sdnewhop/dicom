# DoS in xml2dcm utility

[Global buffer overflow](./data/xml2dcm_global_buffer_overflow_asan.log) was discovered during fuzz-testing of xml2dcm.

## Versions:
* DCMTK 3.6.2 (Linux x64)
* DCMTK 3.6.2 (MacOS x64)

The vendor was informed. The weakness was [fixed](http://git.dcmtk.org/?p=dcmtk.git;a=commit;h=96f4a928c).