# TCGA download
## ATAC-seq download sigle file
```
curl --remote-name --remote-header-name https://api.gdc.cancer.gov/data/b0a4131e-8996-4095-bb27-992747bcce9d
```
## TCGA controlled data download Downloading Controlled-Access Data
A user authentication token is required for downloading Controlled-Access Data from GDC. Tokens can be obtained from the GDC Data Portal (see instructions in Obtaining an Authentication Token). Once downloaded, the token file can be passed to the GDC Data Transfer Tool using the -t or --token-file option:
```
gdc-client download -m gdc_manifest_e24fac38d3b19f67facb74d3efa746e08b0c82c2.txt -t gdc-user-token.2015-06-17T09-10-02-04-00.txt
```
