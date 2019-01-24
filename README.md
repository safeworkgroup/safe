# Secure Archive for eLearning (SAfe)

## Overview
This project defines an open source format, called **Secure Archive for eLearning (SAfe)**, for storing and exchanging eLearning content. It also offers a library of reference implementations written in various popular programming languages to facilitate developers interested in supporting the SAfe format in their applications.

The SAfe Workgroup, which comprises of authors, educators, researchers, and developers from various fields of study, is responsible for maintaining the SAfe format specifications. It is the mission of the SAfe Workgroup to build a platform that promotes the creation, distribution, and consumption of eLearning content in a flexible yet secure manner. 

The SAfe format is designed to provide any eLearning content with the following properties:
* Security: Includes content encryption to prevent unauthorized access as well as authentication to ensure content integrity. 
* Inteoperability: Allows content to be shared across multiple content management/delivery systems. 
* Analytics: Enables real-time content usage tracking.

## Version 1 Specifications
1. SAfe is a subset of JSON (JavaScript Object Notation). Therefore, any valid SAfe document must also be a valid JSON document.

2. A SAfe object is a JSON object with the following **REQUIRED** name/value pairs:
```javascript
  "uid" : "[Unique identifier]",
  "oid" : "[Object identifier]",
  "b64" : "[Base64-encoded encrypted JSON value]",
  "mac" : "[Message authentication code]"
```
  - [RFC 4122](https://tools.ietf.org/html/rfc4122) UUID Version 5 is used by default.
  - [RFC 4648](https://tools.ietf.org/html/rfc4648) Base64 encoding is used by default.
  - [RFC 3602](https://tools.ietf.org/html/rfc3602) AES cipher in CBC mode is used by default.
  - [RFC 2104](https://tools.ietf.org/html/rfc2104) HMAC-SHA1 is used by default.
  
4. A SAfe object can include one or more of the following **OPTIONAL** name/value pairs to facilitate the decryption process:
```javascript
  "cup" : "[Common usage pattern]",
  "key" : {[KeySAfe configuration object]}
```

5. A SAfe object can also include one or more custom name/value pairs   
