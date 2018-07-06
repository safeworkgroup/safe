# Secure Archive for eLearning (SAfe)

## Overview
This project defines an open source file format, called **Secure Archive for eLearning (SAfe)**, for storing and exchanging eLearning content.  It also offers a library of reference implementations written in various popular programming languages to facilitate developers interested in supporting the SAfe format in their applications.

The SAfe Workgroup, which comprises of authors, educators, researchers, and developers from various fields of study, is responsible for maintaining the SAfe format specifications. It is the mission of the SAfe Workgroup to build a platform that promotes the creation, distribution, and consumption of eLearning content in a flexible yet secure manner. 

The defining characteristics of the SAfe format are:
* Open source
* Lightweight
* Extensible
* Secure
* Language agnostic

## Specifications
1. SAfe is a superset of JSON (JavaScript Object Notation). Therefore, any valid JSON document is considered a valid SAfe document.

2. Any JSON value (*object, array, number, string, `true`, `false`, and `null`*) can be encrypted into a SAfe object.

3. A SAfe object is a JSON object with the following **REQUIRED** name/value pairs:
```javascript
{
  "uid" : "[Universally unique identifier]",
  "b64" : "[Base64-encoded encrypted JSON value]",
  "mac" : "[HMAC]",
}
```
