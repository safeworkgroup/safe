# Secure Archive for eLearning (SAfe)

## Overview
This project defines a simple, extensible, machine-readable, human-friendly, and open source format, called **Secure Archive for eLearning (SAfe)**, for storing and exchanging eLearning content. It also offers a library of reference implementations written in various popular programming languages to facilitate developers interested in supporting the SAfe format in their applications.

The SAfe Workgroup, which comprises of authors, educators, researchers, and developers from various fields of study, is responsible for maintaining the SAfe format specifications. It is the mission of the SAfe Workgroup to build a platform that promotes the creation, distribution, and consumption of eLearning content in a flexible yet secure manner. 

The SAfe format is designed to provide any eLearning content with the following properties:
* Security: Includes content encryption to prevent unauthorized access as well as authentication to ensure content integrity. 
* Inteoperability: Allows content to be shared across multiple content management/delivery systems. 
* Analytics: Enables real-time content usage tracking.

## Version 1 General Specification
This section specifies the basic building block and overall structure of the SAfe format.

1. SAfe is a subset of JSON (JavaScript Object Notation). Therefore, any valid SAfe document must also be a valid JSON document.

2. A SAfe object ***MUST*** be a JSON object with the following **REQUIRED** name/value pairs:
```javascript
  "uid" : "[Unique identifier]",
  "tid" : "[Type identifier]",
  "obj" : "[Object content]",
```

3. A SAfe object ***MAY*** include one or more custom name/value pairs for application-specific purposes.

4. [RFC 4122](https://tools.ietf.org/html/rfc4122) UUID Version 5 is used by default for the ```javascript"uid"``` value. It ***MUST*** universally uniquely identifies the SAfe object.

5. The ```javascript"tid"``` value is defined in the following sections. It ***MUST*** provides type information regarding the ```javascript"obj"``` value.

6. The ```javascript"obj"``` value contains the content of the SAfe object. It ***MUST*** matches the type information specified in the ```javascript"tid"``` value. It ***MUST*** be a valid JSON object (*object, array, number, string, `true`, `false`, and `null`*) or a SAfe object.

## Version 1 Type Identifier Specification
The ```javascript"tid"``` type identifier is the most important component of the SAfe format. It specifies how the ```javascript"obj"``` value is to be intepreted, processed, and/or displayed.


  - [RFC 4648](https://tools.ietf.org/html/rfc4648) Base64 encoding is used by default.
  - [RFC 3602](https://tools.ietf.org/html/rfc3602) AES cipher in CBC mode is used by default.
  - [RFC 2104](https://tools.ietf.org/html/rfc2104) HMAC-SHA1 is used by default.
