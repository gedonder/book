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



