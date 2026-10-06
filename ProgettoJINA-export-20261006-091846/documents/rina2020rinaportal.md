---
unique-name: rina2020rinaportal
display-name: RINA 2020 RINA Portal
category: GENERAL
tags: ec
---

<!-- image -->

## EESSI RINA training for developers

RINA 2020 RINA Portal

Day 2 - Afternoon March 2021

## RINA 2020 RINA Portal

<!-- image -->

<!-- image -->

## Structure

- Introduction
- Interaction with other systems
- Rina Portal - Old vs. New
- Design Principles
- Technologies
- Libraries
- Project Structure
- Case study: Clerk starts a new case
- Localisation
- Web Sockets
- Development Practices
- References

<!-- image -->

## Introduction

- Web interface for two types of users

<!-- image -->

<!-- image -->

## Interaction with other systems

<!-- image -->

<!-- image -->

## Rina Portal - Old vs. New

<!-- image -->

<!-- image -->

## Design Principles

- Consistent design:
- Page layout: 12 columns grid
- 3 sections:
- Header
- Main content
- Footer

<!-- image -->

Footer

<!-- image -->

## Design Principles - Header for Clerk

- Title
- Menu
- Case Quick Access

<!-- image -->

<!-- image -->

## Design Principles - Header for Administrator

- Title
- Menu

<!-- image -->

<!-- image -->

## Design Principles - Footer

- Idle timer
- Creation of new case
- Version information

<!-- image -->

## Design Principles - Main content (1)

- Sections:
- Title
- Content
- Toolbar
- 2 types:
- Form layout
- Table layout

<!-- image -->

<!-- image -->

## Design Principles - Main content (2)

- Sections:
- 2 types:
- Table layout

<!-- image -->

<!-- image -->

## Technologies

- New portal - AngularJS end of official support in 2021

<!-- image -->

| Old Portal (up to Rina 5.x)   | New Portal (from 6.x)   |
|-------------------------------|-------------------------|
| AngularJS                     | Angular                 |
| JavaScript                    | TypeScript              |
| CSS                           | SCSS                    |

<!-- image -->

## Libraries- Core libraries

<!-- image -->

<!-- image -->

## Libraries: PrimeNG

- UI Component Library for Angular
- Open source (MIT license)
- Various user controls
- Allows theming (style customization)
- Icons: PrimeIcons
- Framework for Angular application development offered by European Commission, DIGIT
- Provides reusable UI components for a common look and feel across EC projects
- From eUI platform, RINA Portal uses:
- eUI Core
- base library containing the UI components and services used as building blocks for eUI Platform
- eUI Dynamic Forms
- library for generating dynamic forms at runtime based on a metadata description of the form

<!-- image -->

<!-- image -->

<!-- image -->

## Libraries: eUI Platform

<!-- image -->

<!-- image -->

## Libraries: Third-party Libraries

- primeng
- eUI Core
- eUI Dynamic Forms
- fontAwesome
- primeicons
- fullCalendar
- angular-split
- ngx-infinite-scroll
- ngx-toasta
- ngx-ui-loader

## UI components

- sockjs-client
- stompjs
- @ng-idle/core
- @ng-idle/keepalive

Connection management

- @ngx-translate/core
- lodash
- moment
- ngx-clipboard
- rxjs
- subsink
- print-js

## Utilities

<!-- image -->

## Project Structure

## Rina Portal

<!-- image -->

<!-- image -->

## Case Study: Clerk starts a new case

<!-- image -->

<!-- image -->

## Case Study: Clerk starts a new case

<!-- image -->

<!-- image -->

## Authentication &amp; Authorisation (1)

- Authentication
- CAS server
- Session cookie &amp; CSRF token
- Session expiration
- Authorisation
- Angular guards for routing
- HTTP Interceptors:
- Adding CSRF token

<!-- image -->

<!-- image -->

## Authentication &amp; Authorisation (2)

Rina Portal

<!-- image -->

<!-- image -->

## Case Study: Clerk starts a new case

<!-- image -->

<!-- image -->

## Routing (1)

- Move between views by interpreting the URL as an instruction to change view
- Entry component: root module/ from the routing definition
- Eagerly versus lazily loaded modules (feature modules)

E.g. URL: https://RINAPORTAL/case-search

<!-- image -->

<!-- image -->

## Routing (2)

E.g. URL: https://RINAPORTAL/case-search

shared components

User Module

<!-- image -->

<!-- image -->

## Case Study: Clerk starts a new case

<!-- image -->

<!-- image -->

## Case Search view

<!-- image -->

<!-- image -->

## Case Study: Clerk starts a new case

<!-- image -->

<!-- image -->

## Case Action: Choose Participants

<!-- image -->

<!-- image -->

## Case Management - after choosing participants

<!-- image -->

<!-- image -->

## Case Management - during case flow

Case metadata

Case related actions Document related actions

<!-- image -->

<!-- image -->

## Case Study: Clerk starts a new case

<!-- image -->

<!-- image -->

## Document Manager Module - non batch SEDs

<!-- image -->

<!-- image -->

## Document Manager Module - batch SEDs

<!-- image -->

<!-- image -->

## Document Manager Module

## P2000 - Old age pension claim

SED API version: 0.16.3 build preview 1

Model version: 4.2.0

1. Local case numbers

2. INSURED PERSON *

2. Insured person

- 2.1. PERSON IDENTIFICATION *

3. Insured person's e...

2.1.1. Family name(s)

）*

LOVELACE

4. Insured person's be...

5. Spouse

2.1.2. Forename(s)

*

ADA

6. Children

2.1.3. Date of birth *

25/02/1920

7. Information on repr...

8. Information on pay...

2.1.4. Sex

*

- [ ] [01] Male

[02] Female

- [ ] [98] Unknown

9. Miscellaneous

- 2.1.5. Family name(s) at

BYRON

birth

?

- 2.1.6. Forename(s) at birth

<!-- image -->

## SED JSON:

```
{ "P2000": { "InsuredPerson": { "PersonIdentification": { "familyName": "LOVELACE", "forename": "ADA", "dateBirth": "1920-02-25", "sex": { "value": [ "02" ] }, "familyNameAtBirth": "BYRON" } }, "sedGVer": "4", "sedVer": "2", "sedPackage": "Sector Components/Pensions/P2000" } }
```

<!-- image -->

## Document Manager: create &amp; save form

<!-- image -->

## external libraries

Artefacts / data managed by CPI

<!-- image -->

## eUI Metadata

<!-- image -->

<!-- image -->

## eUI Metadata Adaptation

- Service for on-the-fly modifications to eUI metadata in RINA Portal
- Adaptations with focus on presentation aspects
- Activate Forms with Tabs for non-batch SEDs with more than one section
- Activate specific features for all components of a type (e.g. specific start view for Date Picker popups)
- Flexibility for future changes

<!-- image -->

## eUI Metadata - Text Input

## P2000 - Old age pension claim

SED API version: 0.16.3 build preview 1

Model version: 4.2.0

1. Local case numbers

2. INSURED PERSON *

2. Insured person

- 2.1. PERSON IDENTIFICATION *

3. Insured person's e...

2.1.1. Family name(s)

*

LOVELACE

4. Insured person's be...

5. Spouse

2.1.2. Forename(s)

*

ADA

6. Children

2.1.3. Date of birth *

25/02/1920

7. Information on repr...

8. Information on pay...

2.1.4. Sex

*

- [ ] [01] Male

[02] Female

- [ ] [98] Unknown

9. Miscellaneous

2.1.5. Family name(s) at

BYRON

birth

?

- 2.1.6. Forename(s) at birth

<!-- image -->

## Resulting field JSON:

"familyName": "LOVELACE"

## eUI metadata:

```
{ "fieldType" : "formControl", "layout" : { "class" : "col-12" }, "context" : { "type" : "_uxTextInput", "inputs" : { "label" : [ { "string" : "forms.4.2_4965465B-9218-E611-80EA-000C292ED0D7_label", "prefix" : "2.1.1. ", "translate" : true } ], "required" : true }, "key" : "familyName", "validators" : { "validatorFn" : [ { "valFnId" : "groupRequired", "severity" : "danger" }, { "valFnId" : "minLength", "params" : [ 1 ], "severity" : "danger" }, { "valFnId" : "maxLength", "params" : [ 155 ], "severity" : "danger" } ] } } }
```

## Form Validation

- Client-side form validation provided by eUI
- Inline errors
- Errors container with navigable error list
- Types of errors
- Mandatory fields
- Danger - mandatory for saving the form
- Warning - mandatory for sending the form
- Patterns
- Minimum/maximum length, minimum value etc.
- Server-side validation (out of scope) - XSD

<!-- image -->

<!-- image -->

## eUI Customisation

<!-- image -->

Angular libraries

## eUI Custom Components (1)

<!-- image -->

<!-- image -->

## eUI Custom Components (2)

<!-- image -->

<!-- image -->

Commission

## eUI Custom Components (3)

- Institution Repository Search
- Translate container

<!-- image -->

<!-- image -->

<!-- image -->

## eTranslation

- To translate the information from a SED form (different from localisation)

<!-- image -->

<!-- image -->

<!-- image -->

## Localisation

- Key - value
- Localisation for:
- String resources (1)
- Forms (CDM dependent) (2)
- Case actions (2)

<!-- image -->

<!-- image -->

## Web Sockets Notifications

<!-- image -->

(2) After external

changes on case 61

<!-- image -->

## Development Practices

- Scrum / Agile development
- Source control: Git repository (on GitLab server)
- Git workflow: branch for larger features; rebase smaller changes
- Swagger for API
- Pair programming
- Code review
- Docker environment (RINA Server) for testing in development

<!-- image -->

<!-- image -->

<!-- image -->

## EESSI RINA REST API Interface (CPI)

Documentation of the REST calls for operations in the RINA. Contains a list of all REST methods which are used either for the case processing. administration or other operations.

| activity-controller : operations on Activities                        | Show/Hide&#124;   | List Operations   | Expand Operations   |
|-----------------------------------------------------------------------|-------------------|-------------------|---------------------|
| admin-notification-controller : operations on admin                   | Show/Hide         | List Operations   | Expand Operations   |
| alarms-controller : operations on Alarms                              | Show/Hide         | List Operations   | Expand Operations   |
| ap-listener-controller : Ap Listener Controller                       | Show/Hide         | List Operations   | Expand Operations   |
| application-profile-controller : operations on ApplicationProfile     | Show/Hide         | List Operations   | Expand Operations   |
| application-resources-controller : operations on ApplicationResources | Show/Hide         | List Operations   | Expand Operations   |
| assignment-policies-controller : operations on AssignmentPolicies     | Show/Hide         | List Operations   | Expand Operations   |
| attachment-controller : operations on Attachments                     | Show/Hide         | List Operations   | Expand Operations   |
| audit-controller : operations on AuditLogs                            | Show/Hide         | List Operations   | Expand Operations   |
| authentication-controller : Authentication Controller                 | Show/Hide         | List Operations   | Expand Operations   |

business-exceptions-controller : operations on Pending Messages and Business Exceptions

Show/Hide| List Operations Expand Operations

Show/Hide | List Operations Expand Operations

Search cases by parameters

Create new case

Get a case by the business ID

Get a case by the international ID

cases-controller : operations on Cases

<!-- image -->

/Cases

<!-- image -->

<!-- image -->

GET

/Cases

/Cases/ByBusinessld/{businessld}

/Cases/Bylnternationalld/{internationalld}

default (/documentation/v2)

Authorize Explore http://rinaServerURL/eessiRest/swagger-ui.html

<!-- image -->

## References

- https://angular.io/docs
- https://primefaces.org/primeng
- https://eui.ecdevops.eu
- https://eui.ecdevops.eu/eui-showcase-ux-10.x/docs
- https://ec.europa.eu/cefdigital/wiki/display/CEFDIGITAL/eTranslation
- EESSI 2020 - RINA - Architecture Overview
- EESSI 2020 - RINA - Forms Design Specifications
- EESSI 2020 - RINA - Localisation Specifications
- EESSI 2020 - RINA - Case Processing Interface (CPI)
- EESSI 2020 - RINA - CPI Reference Documentation
- EESSI 2020 - RINA - Identity and Access Management (IAM)
- EESSI 2020 - RINA - Functional specs - Case Management
- EESSI 2020 - RINA - Functional specs - Administration portal

<!-- image -->

## Thank you

<!-- image -->

## © European Union 1995 - 2021

Unless otherwise noted the reuse of this presentation is authorised under the CC BY 4.0 license. For any use or reproduction of elements that are not owned by the EU, permission may need to be sought directly from the respective right holders.

<!-- image -->