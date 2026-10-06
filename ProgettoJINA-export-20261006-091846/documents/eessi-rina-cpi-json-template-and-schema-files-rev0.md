---
unique-name: eessi-rina-cpi-json-template-and-schema-files-rev0
display-name: EESSI   RINA   CPI   JSON Template and Schema Files   rev01
category: GENERAL
tags: ec
---

<!-- image -->

<!-- image -->

Employment, Social Affairs andInclusion

## EESSI - RINA

## CPI - JSON TEMPLATE and SCHEMA Files

Operations Guidelines

## Table of Contents

- 1 Introduction ................................................................................................ 5
- 2 JSON Template Files  ..................................................................................... 6
- 3 JSON SCHEMA Files  ...................................................................................... 9
- 3.1 JSON SCHEMA File example  ...................................................................  16

<!-- image -->

<!-- image -->

## Document Control Information

<!-- image -->

| Document Control                     | Value                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project Title                        | Electronic Exchange of Social Security Information (EESSI)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Document Title                       | EESSI - RINA - CPI - JSON Template and Schema Files                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Document Category                    | Operations Manuals & Guides / Operations Guidelines                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Revision                             | rev01                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Component Version                    | -                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Last Publication Date                | 22/12/2021                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Document Status                      | Final                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Sensitivity (TLP) Distribution terms | Traffic Light Protocol (TLP) = ' GREEN ' The distribution of this document is done strictly in line with the Traffic Light Protocol (TLP) established by the European Commission's note AC 790/15 REV for the EESSI project documentation. In line with the note AC 790/15 REV, this document is labelled as TLP = 'Green'. Therefore, it can be circulated widely within the EESSI community. However, the document or the information herein may not be published or posted on the Internet, nor released outside of the EESSI community. |
| Connected/Embedded Files             | None                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Authors                              | European Commission, DG EMPL A4, EESSI ARCH/RINA                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Revised by                           | European Commission, DG EMPL A4, EESSI QA                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Approved by                          | European Commission, DG EMPL A4, EESSI PMO                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

## Document history

| Project Milestone   | Date       | Changes/Corrections Description     |
|---------------------|------------|-------------------------------------|
| EESSI-2019          | 30/11/2019 | Initial Document                    |
| EESSI-2020 rev01    | 22/12/2021 | Adjusted to last CPI implementation |

<!-- image -->

## 1 Introduction

To support the countries participating in the EESSI project in managing the communication with RINA CPI, the following JSON files are generated (for documentation purpose):

- The SEDs payload structure, referred to as JSON TEMPLATE files;
- Description of the SED payload structure (i.e., JSON TEMPLATE), referred to as JSON SCHEMA.

Note :  This  document  applies  for  JSON  TEMPLATE  and  JSON  SCHEMA  files  delivered together with CDM 4.1. and 4.2.

<!-- image -->

## 2 JSON Template Files

JSON TEMPLATE files are generated per SED and they contain the full possible SED object payload structure. An example of the form for X001 SED is provided in Figure 1, which will be used as main example within this document.

Figure 1 - X001 SED form

<!-- image -->

For X001 SED following JSON TEMPLATE is generated:

<!-- image -->

<!-- image -->

```
{ "X001" :{ "sedPackage" : "Sector Components/Administrative/X001" , "sedGVer" : "4" , "sedVer" : "2" , "CaseContext" :{ "PersonContext" :{ "familyName" : "" , "forename" : "" , "dateBirth" : "" , "sex" : "" }, "EmployerContext" :{ "name" : "" , "IdentificationNumbers" :{ "IdentificationNumber" :[{ "number" : "" , "type" : "" }] }, "Address" :{ "street" : "" , "buildingName" : "" , "town" : "" , "postalCode" : "" , "region" : "" , "country" : "" } }, "ReimbursementContext" :{ "reimbursementRequestID" : "" , "totalNumberIndividualClaims" : "" } }, "InformationAboutClose" :{ "closeDate" : "" , "close" : "" , "reasonForClosing" : "" , "pleaseProvideMoreDetailsIf99OtherSelected" : "" } } }
```

Figure 2 - X001 JSON Template

Note: The JSON TEMPLATE file contains the full SED payload structure, where all the choice options (e.x. in case of X002 these are PersonContext, EmployerContext and ReimbursementContext) are present. A valid JSON payload corresponding to an SED will have only one of the choices selected, as noticeable from Figure 3. The data-model XSD definition of the SED will restrict in the actual XML data exchanges for the presence of only one of the choices (this means that the XSD interpretation cannot be bypassed).

<!-- image -->

```
{ "X001" : { "sedPackage" : "Sector Components/Administrative/X001" , "sedGVer" : "4" , "sedVer" : "2" , " CaseContext" : { "PersonContext" : { "familyName" : "Family" , "forename" : "Forename" , "dateBirth" : "2000-01-01" , "sex" : { "value" : [ "01" ] } } }, "InformationAboutClose" : { "closeDate" : "2020-12-31" , "close" : { "value" : [ "01" ] }, "reasonForClosing" : { "value" : [ "99" ] }, "pleaseProvideMoreDetailsIf99OtherSelected" : "Example only" } } }
```

Figure 3 - Example of valid SED JSON payload for X001

## 3 JSON SCHEMA Files

JSON SCHEMA like files are generated to assist the interpretation process of the SED JSON TEMPLATES. These SEDs JSON SCHEMA-like files contain for each element (section or data input) meta-data information using a list of $$meta\_properties in the format:

```
"fieldTechnicalName1" : { "$$meta_property1" : "value" , "$$meta_property2" : "value" , … }, … "fieldTechnicalNameN" : { "$$meta_property1" : "value" , "$$meta_property2" : "value" , … }
```

Figure 4 - Meta-data information structure in JSON SCHEMA

The following list of $$meta\_property are generated:

## ➢ $$type

- Type of the element.
- The property can have the following values:
- o "sed" : this type is for the SED itself (root entry of the JSON)
- o "section" : field is a section / sub-section (non-input data field)
- o "enum" : field is an enumeration (value selectable from a pre-defined list)
- o User input data fields like XSD primitive types:
- ־ ' string ' : field is a string (character strings)
- ־ ' int ' : field is an integer number
- ־ ' double ' : field is a floating-point number
- ־ ' date ' : field is a calendar date

## Example :

```
' $$type ' : ' string '
```

Figure 5 - Example for meta-property $$type

<!-- image -->

Note #1 : For the enum type of element, the actual value in the SED JSON object is not a simple string but a complex object in the form:

```
' enumFieldName ' : { ' value ' : [ ' value1 ' , ' value2 ' , … ] }
```

## Example :

```
"sex" : { "value" : ["02"] }  instead of "sex" : "02"
```

Figure 6 - Example #1 of valid SED JSON corresponding to "enum" with 1 value

Or

```
"nationality" : { "value" : ["AT","BE"] }
```

Figure 7 - Example #2 of valid SED JSON corresponding to "enum" with multiple values

<!-- image -->

This  structure  for  the  enumeration  values  stems  from  'XSD  Format  Specifications' document which can be consulted for further details.

Note #2: Each input data field value should be within double quotes.

For example in the context of the U020 SED content, field 2.2 is an ' int ' .

Figure 8 - Excerpt from U020 SED form

<!-- image -->

```
"numberIndividualClaims" :{ "$$name" : "numberIndividualClaims" , "$$heading" : "2.2" , "$$mandatory" : true , "$$repetition" : false , "$$hasRestrictions" : true , "$$restrictions" :{ "minInclusive" : "0" }, "$$type":"int" }
```

Figure 9 - Meta-information for element 2.2 from U020 SED

The correct value in JSON payload object is:

```
"numberIndividualClaims": "2" instead of "numberIndividualClaims": 2
```

Figure 10 - Example of valid SED JSON payload corresponding to "int"

```
"numberIndividualClaims": ""
```

Figure 11 - Example of valid SED JSON payload for empty input field, in this case "int"

Note #3: Empty sections should  be  represented  as  empty  JSON  objects  or  as  JSON objects with empty objects (for the elements within the section).

Example:

For PersonContext section within X001, the JSON SCHEMA looks like in Figure 12

"PersonContext" :{

<!-- image -->

```
"$$name" : "PersonContext" , "$$heading" : "1.1" , "$$mandatory" :true, "$$repetition" :false, "$$choice" : 1 , "$$choiceIndex" : 0 , "$$type" : "section" , "familyName" :{ "$$name" : "familyName" , "$$heading" : "1.1.1" , "$$mandatory" :true, "$$repetition" :false, "$$restrictions" : { "minLength" : "1" , "maxLength" : "155" }, "$$type" : "string" }, "forename" :{ … }, "dateBirth" :{ … }, "sex" :{ … } }
```

Figure 12 - Excerpt from JSON SCHEMA for X001 for PersonContext section (simplified - the children within the section are not listed completely)

Correct values for an empty PersonContext section should look like in Figure 13 or Figure 14.

```
"PersonContext": {} Figure 13 Correct JSON payload for empty 'section' empty object
```

Figure 14 Correct JSON payload for empty 'section' object with empty objects

```
"PersonContext" : { "familyName" : "" , "forename" : "" , "dateBirth" : "" , "sex" : {} }
```

For e.g., empty sections should not be represented as empty strings, as in Figure 15.

```
"PersonContext": ''
```

Figure 15 - Incorrect JSON payload for empty "section"

Note #4: In case of enum type Rina CPI and RINA Portal accept that JSON array with one object only is provided as JSON object.

## Example :

The correct representation is:

```
{ "country": { "value": [ "SE" ]}
```

Figure 16 - Correct JSON payload for "enum" with one value only

The following representation (square brackets missing) is, however, accepted:

```
{ "country": { "value": "SE" }
```

Figure 17 - Accepted representation in JSON payload for "enum" with one value only

This applies for all enumeration fields ( "enum" type).

## ➢ $$name

- The value of this $$meta\_property is the same as the technical field. It is added here to have it accessible at the scope level of the other meta properties for the field.

## Example :

```
"$$name" : "X001"
```

Figure 18 - Example for meta-property $$name

## ➢ $$restrictions

- If the property is present, then restrictions for the field are specified in the format:
- The following restriction types can be applied:
- o "maxInclusive ': upper  bounds for  numeric values, i.e.  value  must  be  less than or equal to this value;
- o "minInclusive ': lower bounds for numeric values, i.e. value must be greater than or equal to this value
- o "maxLength ': maximum number of characters (must be equal to or greater than zero)
- o "minLength ': minimum number of characters (must be equal to or greater than zero)
- o "pattern ': the exact sequence of characters that are acceptable (in Regular Expression format)

```
{ "restrictionType1" : "value" , "restrictionType2" : "value", … }
```

## Example :

```
"$$restrictions" : { ' minLength" : "1" , "maxLength" : "155"
```

Figure 19 - Example for meta-property $$restrictions with minimum and maximum number of characters

```
}
```

```
"$$restrictions" : { "pattern" : "(AT|BE|BG|HR|CY|CZ|DK|EE|FI|FR|DE|EL|HU|IS|IE|IT|LV|LI|LT|LU|M T|NL|NO|PL|PT|RO|SK|SI|ES|SE|CH|UK|EU):[a-zA-Z0-9]{4,10}" }
```

Figure 20 - Example for meta-property $$restrictions with accepted sequence of characters

## ➢ $$mandatory

- Shows if the field is marked as mandatory or not.
- The property can have the following values:
- o true: the field is marked as mandatory
- o false: the field is NOT marked as mandatory (it is optional)

<!-- image -->

## Example :

"$$mandatory" : true

Figure 21 - Example for meta-property $$mandatory

Note : Mandatory (or Optional if the value of the property is false ) is a state that applies to both fields (input data field) and sections (non-input data field). This means that a field can either be Mandatory or Optional and a section can also be Mandatory or Optional.

The  'actual  mandatory'  (meaning  that  the  field  must  contain  actual  data  to  pass  the validation) state of a field depends also on the context in which the field appears in the SED structure and its behavior is the following one:

- if the field is marked as mandatory then if the section where the field is located is nested inside another section or in case of multiple nested sections, then the state of the field is 'actual mandatory' only if all its above parent sections are also marked as mandatory

OR

- if the field is marked as mandatory and if the parent section of the field 'has actual data' (there is at least one sibling field in the section that contains data) then the state of the field is 'actual mandatory'

This state needs to be computed dynamically for each field and it must consider the actual data which is present in the SED together with its $$mandatory property.

## ➢ $$repetition

- Shows if the section is repetitive or not.
- The property can have the following values:

- o

- true: the section is repetitive

- o false: the section is NOT repetitive

## Example :

```
"$$repetition" : true
```

Figure 22 - Example for meta-property $$repetition

Note: Repetitive sections are stored in JSON arrays. Rina CPI and RINA Portal accept cases when a repetitive section with only one element within is provided in the JSON payload as an JSON object instead of JSON array with one element only.

<!-- image -->

Figure 23 - Example of repetitive section from H001 SED

<!-- image -->

<!-- image -->

Figure 24 - Excerpt from JSON SCHEMA for H001 SED containing a repetitive section

<!-- image -->

The correct representation for OtherDocuments object is:

## ➢ $$fixedValue

- If present, then this is the value (if the field is present in the data, then it has this value) for the field.

## Example :

```
"$$fixedValue" : "1"
```

Figure 28 - Example for meta-property $$fixedValue

## ➢ $$choice

- If present, it means that the element is a choice, and the value is the choice group identifier (starts from 1) to which this choice belongs.

## Example :

```
"$$choice" : "1"
```

<!-- image -->

Figure 25 - Correct JSON payload for repetitive section with one entry only

<!-- image -->

The following representation (square brackets missing, i.e., object instead of array with one object only) is, however, accepted:

```
"OtherDocumentsAttached" : { "OtherDocument" :{ "document" : "First document" } }
```

Figure 26 - Accepted JSON payload for repetitive section with one entry only

## ➢ $$heading

- A string value that will contain the heading. The heading is the hierarchical numbering or sequence number that prefixes the section/field name.

## Example :

```
"$$heading" : "1.1.2"
```

Figure 27 - Example for meta-property $$heading

Figure 29 - Example for meta-property $$choice

## ➢ $$choice\_index

- If present, the value is the index of this choice (starts from 0) inside the choice group.

## Example :

```
"$$choice_index" : "0"
```

Figure 30 - Example for meta-property $$choice\_index

## 3.1 JSON SCHEMA File example

The JSON SCHEMA file corresponding to JSON TEMPLATE of X001 displayed in Figure 2 is the following:

```
{ "X001" : { "$$name" : "X001" , "$$heading" : "" , "$$mandatory" :true, "$$repetition" :false, "$$type" : "sed" , "CaseContext" :{ "$$name" : "CaseContext" , "$$heading" : "1" , "$$mandatory" :true, "$$repetition" :false, "$$type" : "section" , "PersonContext" :{ "$$name" : "PersonContext" , "$$heading" : "1.1" , "$$mandatory" :true, "$$repetition" :false, "$$choice" : 1 , "$$choiceIndex" : 0 , "$$type" : "section" , "familyName" :{ "$$name" : "familyName" , "$$heading" : "1.1.1" , "$$mandatory" :true, "$$repetition" :false, "$$restrictions" : { "minLength" : "1" , "maxLength" : "155" }, "$$type" : "string" }, "forename" :{ "$$name" : "forename" , "$$heading" : "1.1.2" , "$$mandatory" :true, "$$repetition" :false, "$$restrictions" : { "minLength" : "1" , "maxLength" : "155" }, "$$type" : "string" },
```

<!-- image -->

<!-- image -->

```
"dateBirth" :{ "$$name" : "dateBirth" , "$$heading" : "1.1.3" , "$$mandatory" :true, "$$repetition" :false, "$$type" : "date" }, "sex" :{ "$$name" : "sex" , "$$heading" : "1.1.4" , "$$mandatory" :true, "$$repetition" :false, "$$type" : "enum" } }, "EmployerContext" :{ "$$name" : "EmployerContext" , "$$heading" : "1.2" , "$$mandatory" :true, "$$repetition" :false, "$$choice" : 1 , "$$choiceIndex" : 1 , "$$type" : "section" , "name" :{ "$$name" : "name" , "$$heading" : "1.2.1" , "$$mandatory" :true, "$$repetition" :false, "$$restrictions" : { "minLength" : "1" , "maxLength" : "155" }, "$$type" : "string" }, "IdentificationNumbers" :{ "$$name" : "IdentificationNumbers" , "$$heading" : "1.2.2" , "$$mandatory" :false, "$$repetition" :false, "$$type" : "section" , "IdentificationNumber" :[{ "$$name" : "IdentificationNumber" , "$$heading" : "1.2.2.1" , "$$mandatory" :false, "$$repetition" :true, "$$type" : "section" , "number" :{ "$$name" : "number" , "$$heading" : "1.2.2.1.1" , "$$mandatory" :true, "$$repetition" :false, "$$restrictions" : { "minLength" : "1" , "maxLength" : "25" }, "$$type" : "string" }, "type" :{
```

<!-- image -->

```
"$$name" : "type" , "$$heading" : "1.2.2.1.2" , "$$mandatory" :true, "$$repetition" :false, "$$type" : "enum" } }] }, "Address" :{ "$$name" : "Address" , "$$heading" : "1.2.3" , "$$mandatory" :false, "$$repetition" :false, "$$type" : "section" , "street" :{ "$$name" : "street" , "$$heading" : "1.2.3.1" , "$$mandatory" :false, "$$repetition" :false, "$$restrictions" : { "minLength" : "1" , "maxLength" : "155" }, "$$type" : "string" }, "buildingName" :{ "$$name" : "buildingName" , "$$heading" : "1.2.3.2" , "$$mandatory" :false, "$$repetition" :false, "$$restrictions" : { "minLength" : "1" , "maxLength" : "155" }, "$$type" : "string" }, "town" :{ "$$name" : "town" , "$$heading" : "1.2.3.3" , "$$mandatory" :true, "$$repetition" :false, "$$restrictions" : { "minLength" : "1" , "maxLength" : "65" }, "$$type" : "string" }, "postalCode" :{ "$$name" : "postalCode" , "$$heading" : "1.2.3.4" , "$$mandatory" :false, "$$repetition" :false, "$$restrictions" : { "minLength" : "1" , "maxLength" : "25" }, "$$type" : "string" }, "region" :{ "$$name" : "region" , "$$heading" : "1.2.3.5" , "$$mandatory" :false, "$$repetition" :false, "$$restrictions" : { "minLength" : "1" , "maxLength" : "65" },
```

<!-- image -->

```
"$$type" : "string" }, "country" :{ "$$name" : "country" , "$$heading" : "1.2.3.6" , "$$mandatory" :true, "$$repetition" :false, "$$type" : "enum" } } }, "ReimbursementContext" :{ "$$name" : "ReimbursementContext" , "$$heading" : "1.3" , "$$mandatory" :true, "$$repetition" :false, "$$choice" : 1 , "$$choiceIndex" : 2 , "$$type" : "section" , "reimbursementRequestID" :{ "$$name" : "reimbursementRequestID" , "$$heading" : "1.3.1" , "$$mandatory" :true, "$$repetition" :false, "$$type" : "string" }, "totalNumberIndividualClaims" :{ "$$name" : "totalNumberIndividualClaims" , "$$heading" : "1.3.2" , "$$mandatory" :true, "$$repetition" :false, "$$restrictions" : { "minInclusive" : "0" }, "$$type" : "int" } } }, "InformationAboutClose" :{ "$$name" : "InformationAboutClose" , "$$heading" : "2" , "$$mandatory" :true, "$$repetition" :false, "$$type" : "section" , "closeDate" :{ "$$name" : "closeDate" , "$$heading" : "2.1" , "$$mandatory" :true, "$$repetition" :false, "$$type" : "date" }, "close" :{ "$$name" : "close" , "$$heading" : "2.2" , "$$mandatory" :true,
```

<!-- image -->

```
"$$repetition" :false, "$$type" : "enum" }, "reasonForClosing" :{ "$$name" : "reasonForClosing" , "$$heading" : "2.3" , "$$mandatory" :true, "$$repetition" :false, "$$type" : "enum" }, "pleaseProvideMoreDetailsIf99OtherSelected" :{ "$$name" : "pleaseProvideMoreDetailsIf99OtherSelected" , "$$heading" : "2.4" , "$$mandatory" :false, "$$repetition" :false, "$$restrictions" : { "minLength" : "1" , "maxLength" : "255" }, "$$type" : "string" } } } }
```

Figure 31 - JSON SCHEMA for X001 SED

## Table of figures

| Figure 1 - X001 SED form.........................................................................                                                                                        | 6                            |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------|
| Figure 2 - X001 JSON Template .................................................................                                                                                          | 7                            |
| Figure 3 - Example of valid SED JSON payload for X001.................................                                                                                                   | 8                            |
| Figure 4 - Meta-data information structure in JSON SCHEMA                                                                                                                                | .......................... 9 |
| Figure 5 - Example for meta-property $$type...............................................                                                                                               | 9                            |
| Figure 6 - Example #1 of valid SED JSON corresponding to "enum" with 1 value                                                                                                             | 9                            |
| Figure 7 - Example #2 of valid SED JSON corresponding to "enum" with multiple values ................................................................................................... | 9                            |
| Figure 8 - Excerpt from U020 SED form ....................................................                                                                                               | 10                           |
| Figure 9 - Meta-information for element 2.2 from U020 SED.........................                                                                                                       | 10                           |
| Figure 10 - Example of valid SED JSON payload corresponding to "int"...........                                                                                                          | 10                           |
| Figure 11 - Example of valid SED JSON payload for empty input field, in this                                                                                                             |                              |
| case "int" ....................................................................................................                                                                          | 10                           |
| (simplified - the children within the section are not listed completely) ............ Figure 13 - Correct JSON payload for empty 'section' - empty object ............                   | 11 11                        |
| Figure 14 - Correct JSON payload for empty 'section' - object with empty objects ................................................................................................        | 11                           |
| Figure 15 - Incorrect JSON payload for empty "section" ...............................                                                                                                   | 11                           |
| Figure 16 - Correct JSON payload for "enum" with one value only .................                                                                                                        | 11                           |
| Figure 17 - Accepted representation in JSON payload for "enum" with one value only ....................................................................................................  | 11                           |
| Figure 18 - Example for meta-property $$name .........................................                                                                                                   | 12                           |
| Figure 19 - Example for meta-property $$restrictions with minimum and........                                                                                                            | 12                           |
| Figure 20 - Example for meta-property $$restrictions with accepted ..............                                                                                                        | 12                           |
| Figure 21 - Example for meta-property $$mandatory ..................................                                                                                                     | 13                           |
| Figure 22 - Example for meta-property $$repetition....................................                                                                                                   | 13                           |
| Figure 23 - Example of repetitive section from H001 SED.............................                                                                                                     | 14                           |
| Figure 24 - Excerpt from JSON SCHEMA for H001 SED containing a repetitive section.................................................................................................       | 14                           |
| Figure 25 - Correct JSON payload for repetitive section with one entry only ....                                                                                                         | 15                           |
| Figure 26 - Accepted JSON payload for repetitive section with one entry only..                                                                                                           | 15                           |
| Figure 27 - Example for meta-property $$heading ......................................                                                                                                   | 15                           |
| Figure 28 - Example for meta-property $$fixedValue...................................                                                                                                    | 15                           |
| Figure 29 - Example for meta-property $$choice ........................................                                                                                                  | 15                           |
| Figure 30 - Example for meta-property $$choice_index ...............................                                                                                                     | 16                           |
| Figure 31 - JSON SCHEMA for X001 SED ...................................................                                                                                                 | 20                           |

<!-- image -->