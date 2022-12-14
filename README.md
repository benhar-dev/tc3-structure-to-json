# Simple example of converting a structure to Json using FB_JsonReadWriteDataType

## Disclaimer
This is a personal guide not a peer reviewed journal or a sponsored publication. We make
no representations as to accuracy, completeness, correctness, suitability, or validity of any
information and will not be liable for any errors, omissions, or delays in this information or any
losses injuries, or damages arising from its display or use. All information is provided on an as
is basis. It is the reader’s responsibility to verify their own facts.

The views and opinions expressed in this guide are those of the authors and do not
necessarily reflect the official policy or position of any other agency, organization, employer or
company. Assumptions made in the analysis are not reflective of the position of any entity
other than the author(s) and, since we are critically thinking human beings, these views are
always subject to change, revision, and rethinking at any time. Please do not hold us to them
in perpetuity.

## Overview 
This is a simple example showing how to use [FB_JsonReadWriteDataType](https://infosys.beckhoff.com/english.php?content=../content/1033/tcplclib_tc3_jsonxml/4220231435.html).  This example would also work with primitive datatypes and arrays.    

## Screenshot
![image](./docs/images/Screenshot.png)

## Code Snippets
You can copy and past the example code from here... 
```
PROGRAM MAIN
VAR
	
	testVariable : MyExampleStructure;	
	transform : FB_JsonReadWriteDataType;
	datatypeName : STRING(100); 
	resultingJsonStringLength : UDINT;  
	jsonString : STRING(1000);

END_VAR
```
```
datatypeName := transform.GetDataTypeNameByAddress(SIZEOF(testVariable),ADR(testVariable));

resultingJsonStringLength := transform.GetSizeJsonStringFromSymbol(datatypeName,SIZEOF(testVariable),ADR(testVariable));

transform.CopyJsonStringFromSymbol(datatypeName,SIZEOF(testVariable), ADR(testVariable),jsonString,SIZEOF(jsonString));

```
## Versions
* TcXaeShell 3.1.4024.35

## Need more help?
Please visit http://beckhoff.com/ for further guides
