# E-Books epubs 
Decrypt epub files


## What is DRM?
Digital Rights Management or DRM is a scheme that controls access to copyrighted material using technological means. It may refer to the usage of proprietary software, hardware, or any type of content: music tracks, video files, ebooks, games, DVD movies, emails, documents, etc.

ACSM files are Adobe DRM protected files.

protected ePub files can only be opened using Adobe Digital Editions (ADE) on your PC/Mac. Please follow the steps to download Adobe Digital Edition: Goto http://www.adobe.com/products/digitaleditions/ Click the install badge to download and install the latest version of Digital Editions.


## Activation 
Where are my keys and activation of Adobe. 
<br>
˜/Library/Application Support/Adobe/Digital Editions/activation.dat 

The format of the file is defined in a namespace:
namespaces = {'adept': 'http://ns.adobe.com/adept'}
This information is used to unpack the xml file.

In the XML find the tag:
//{%s}credentials/{%s}privateLicenseKey'  this is the place where your private key is.

Take the privateKey

* Add '-----BEGIN PRIVATE KEY-----' 
* Append '-----END PRIVATE KEY-----'
* Run: openssl rsa -outform der>out.der and add the data above to make a certificate file

## EPUB

EPUB file is a zip file containing lots of files. Example:
```

M Filemode      Length  Date         Time      File
- ----------  --------  -----------  --------  ----------------------------
  -rw-rw-rw-        20  31-Oct-2017  18:19:30  mimetype
  -rw-rw-rw-     10371               00:00:00  META-INF/encryption.xml
  -rw-rw-rw-       265  31-Oct-2017  18:19:30  META-INF/container.xml
  -rw-rw-rw-      3996  31-Oct-2017  18:19:30  OEBPS/content.opf
  -rw-rw-rw-    540928  31-Oct-2017  18:19:30  OEBPS/Images/CoverDesign.jpg
  -rw-rw-rw-      4896  31-Oct-2017  18:19:30  OEBPS/Images/image0.jpg
  -rw-rw-rw-       976  31-Oct-2017  18:19:30  OEBPS/Styles/styles.css
  -rw-rw-rw-       400  31-Oct-2017  18:19:30  OEBPS/Text/CoverPage.html
  -rw-rw-rw-       720  31-Oct-2017  18:19:30  OEBPS/Text/section-0001.html
  -rw-rw-rw-      8816  31-Oct-2017  18:19:30  OEBPS/Text/section-0002.html
  -rw-rw-rw-      6816  31-Oct-2017  18:19:30  OEBPS/Text/section-0003.html
  -rw-rw-rw-     10480  31-Oct-2017  18:19:30  OEBPS/Text/section-0004.html
  -rw-rw-rw-       720  31-Oct-2017  18:19:30  OEBPS/toc.ncx
  -rw-rw-rw-      3197               00:00:00  META-INF/rights.xml
- ----------  --------  -----------  --------  ----------------------------
                681289                         27 files

```

The rights.xml contains de keys of the book.
