---
unique-name: eessi-rina-continuous-delivery-environments-layer2
display-name: EESSI   RINA   Continuous Delivery Environments (Layer2 Layer3 PL1)   rev01
category: GENERAL
tags: ec
---

<!-- image -->

<!-- image -->

EESSI -RINA

## Continuous Delivery Environments

Layer 2, Layer 3 &amp; Production-Like (L2/L3/PL)

Operations Manuals &amp; Guides

Employment, Social Affairs andInclusion

## Contents

| 1 Introduction ....................................................................................................   | 1 Introduction ....................................................................................................   | 1 Introduction ....................................................................................................   | 5                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| 1.1 Overview ...................................................................................................      | 1.1 Overview ...................................................................................................      | 1.1 Overview ...................................................................................................      | 5                                                                                                    |
| 1.2 Document Scope.........................................................................................           | 1.2 Document Scope.........................................................................................           | 1.2 Document Scope.........................................................................................           | 5                                                                                                    |
| 1.3 Definitions, Acronyms and Abbreviations........................................................                   | 1.3 Definitions, Acronyms and Abbreviations........................................................                   | 1.3 Definitions, Acronyms and Abbreviations........................................................                   | 5                                                                                                    |
| 1.4 Reference and Applicable documents .............................................................                  | 1.4 Reference and Applicable documents .............................................................                  | 1.4 Reference and Applicable documents .............................................................                  | 6                                                                                                    |
| 1.5 Out of Scope ..............................................................................................       | 1.5 Out of Scope ..............................................................................................       | 1.5 Out of Scope ..............................................................................................       | 6                                                                                                    |
| 2 EESSI Continuous Delivery environments architecture ..........................................                      | 2 EESSI Continuous Delivery environments architecture ..........................................                      | 2 EESSI Continuous Delivery environments architecture ..........................................                      | 7                                                                                                    |
| 2.1 L2 Continuous Delivery environment .............................................................                  | 2.1 L2 Continuous Delivery environment .............................................................                  | 2.1 L2 Continuous Delivery environment .............................................................                  | 7                                                                                                    |
| 2.1.1 Overview..............................................................................................          | 2.1.1 Overview..............................................................................................          | 2.1.1 Overview..............................................................................................          | 7                                                                                                    |
| 2.1.2 Scope of L2 environment and tests ..........................................................                    | 2.1.2 Scope of L2 environment and tests ..........................................................                    | 2.1.2 Scope of L2 environment and tests ..........................................................                    | 8                                                                                                    |
| 2.2 L3 Continuous Delivery environment .............................................................                  | 2.2 L3 Continuous Delivery environment .............................................................                  | 2.2 L3 Continuous Delivery environment .............................................................                  | 8                                                                                                    |
| 2.2.1 Overview..............................................................................................          | 2.2.1 Overview..............................................................................................          | 2.2.1 Overview..............................................................................................          | 8                                                                                                    |
| 2.2.2 Scope of L3 Environment and Tests .........................................................                     | 2.2.2 Scope of L3 Environment and Tests .........................................................                     | 2.2.2 Scope of L3 Environment and Tests .........................................................                     | 9                                                                                                    |
| 2.3 PL Continuous Delivery environment.............................................................10                 | 2.3 PL Continuous Delivery environment.............................................................10                 | 2.3 PL Continuous Delivery environment.............................................................10                 |                                                                                                      |
| 2.3.1 Overview.............................................................................................10         | 2.3.1 Overview.............................................................................................10         | 2.3.1 Overview.............................................................................................10         |                                                                                                      |
| 2.3.2 Scope of Production-like (PL) environment and Tests ................................11                          | 2.3.2 Scope of Production-like (PL) environment and Tests ................................11                          | 2.3.2 Scope of Production-like (PL) environment and Tests ................................11                          |                                                                                                      |
| 3 EESSI Continuous Delivery Environments infrastructure deployment .....................12                            | 3 EESSI Continuous Delivery Environments infrastructure deployment .....................12                            | 3 EESSI Continuous Delivery Environments infrastructure deployment .....................12                            |                                                                                                      |
| 3.1                                                                                                                   |                                                                                                                       | Overview                                                                                                              | ..................................................................................................12 |
| 3.2                                                                                                                   |                                                                                                                       | EESSI CD infrastructure deployment configuration                                                                      | .........................................12                                                          |
| 3.3                                                                                                                   |                                                                                                                       | L2 infrastructure deployment configuration files                                                                      | .............................................14                                                      |
| 3.4                                                                                                                   |                                                                                                                       | L3 infrastructure deployment configuration files .............................................15                      |                                                                                                      |
| 3.5                                                                                                                   |                                                                                                                       | PL infrastructure deployment configuration files .............................................15                      |                                                                                                      |
| 4                                                                                                                     | EESSI                                                                                                                 | Continuous Delivery Environments applications deployment........................17                                    |                                                                                                      |

<!-- image -->

<!-- image -->

## Document Control Information

| Document Control                        | Value                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Project Title                           | Electronic Exchange of Social Security Information (EESSI)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Document Name                           | EESSI - RINA - Continuous Delivery (CD) Environments (L2/L3/PL)                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Document Category                       | Operations Manuals & Guides                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Revision                                | rev01                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Component Version                       | RINA 6.2.18                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Last Publication Date Project Milestone | 22/12/2021 EESSI-2020 HF8                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Document Status                         | Draft                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Sensitivity (TLP) Distribution terms    | Traffic Light Protocol (TLP) = ' GREEN ' The distribution of this document is done strictly in line with the Traffic Light Protocol (TLP) established by the European Commission's note AC 790/15 REV for the EESSI project documentation. In line with the note AC 790/15 REV, this document is labelled as TLP = 'Green'. Therefore, it can be circulated widely within the EESSI community. However, the document or the information herein may not be published or posted on the Internet, nor released outside of the EESSI community. |
| Connected/Embedded Files                | None                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Authors                                 | European Commission, DG EMPL A4, EESSI RINA                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Revised by                              | European Commission, DG EMPL A4, EESSI QA                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Approved by                             | European Commission, DG EMPL A4, EESSI PM                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

## Document History

| Project Milestone   | Date       | Changes/Corrections Description                                                    |
|---------------------|------------|------------------------------------------------------------------------------------|
| EESSI 2020          | 16/04/2021 | Initial Document                                                                   |
| EESSI 2020          | 22/12/2021 | Reviewed for CD status up to RINA 2020 EESSI- 2020 HF8 (RINA 6.2.18/Portal 6.2.19) |

<!-- image -->

## 1 Introduction

## 1.1 Overview

In the process of delivering RINA with a lot of changes and improvements in short period of time, a CI/CD delivery pipeline is needed that ensures:

- repeatability of builds.
- an efficient QA process.

In this context the Layer 2 (L2), Layer 3 (L3) and Production-Like (PL) Continuous Delivery was developed.

- L2, L3 and PL environments are used to improve the quality of the delivered RINA, Access Points and Central Service Node software components and to test all the applicable testing scenarios.

L2 and L3 as well as L1 ( ' EESSI -RINA -Continuous Integration Environments (Layer 1) ' ) act as quality gates and are intended to identify bugs by increasing the number of scenarios and tests with each release promotion.

## 1.2 Document Scope

This  document  describes  the  EESSI  Continuous  Delivery  (CD)  environments,  their structural components and the related configuration.

It also describes the way EESSI Testing environments are deployed and configured. There are three EESSI CD environments: Continuous Delivery Layer 2 (L2) and Layer 3 (L3) Environments and Production-Like Continuous Delivery Environment (PL).

The document is not specific to RINA. The EESSI Central Team conducts many testing activities  in  parallel  due  to  the  many  changes  that  are  implemented  in  the  various components of the system and this impacts the size  of the infrastructure necessary to perform those testing activities.

## 1.3 Definitions, Acronyms and Abbreviations

| Abbreviation   | Full Form                                        |
|----------------|--------------------------------------------------|
| BMI            | Business Messaging Interface                     |
| CI             | Continuous Integration                           |
| CD             | Continuous Delivery                              |
| CPI            | Case Processing Interface                        |
| L1/L2/L3       | Layer 1/ Layer 2/Layer 3                         |
| NIE            | National Information Exchange Interface          |
| PL             | Production-Like                                  |
| RINA           | Reference Implementation of National Application |
| UI             | User Interface                                   |

| Term      | Definition                                                                                                                         |
|-----------|------------------------------------------------------------------------------------------------------------------------------------|
| RINA 2019 | The term RINA 2019 is used to described RINA ver. 5.6.4 or higher                                                                  |
| RINA 2020 | The term RINA 2020 is used for RINA delivery (KIT) of EESSI 2020 release and includes RINA 6.2.18 and RINA Portal 6.2.19 and later |

<!-- image -->

## 1.4 Reference and Applicable documents

| #   | Artefact/Document                                            |
|-----|--------------------------------------------------------------|
| R1  | EESSI - RINA - Continuous Integration Environments (Layer 1) |

## 1.5 Out of Scope

This document describes the currently used technologies and workflow of the existing implementation ( ' as-is ' situation) that are related to RINA. Deployment and configuration of the CSN and AP components is not described.

<!-- image -->

<!-- image -->

## 2 EESSI Continuous Delivery environments architecture

## 2.1 L2 Continuous Delivery environment

## 2.1.1 Overview

The scope of the L2 CD environment is the testing of RINA installation in a single node setup.  Since  the  majority  of  RINA  deployments  are  on  Windows  Servers,  the  L2 environment is comprised exclusively of Windows Server 2016 Datacenter servers.

<!-- image -->

|   No. | Name      | Compone nt   | Versio n   | AP      | Tenant                                                | Transport Mode (Push/Pull)   |
|-------|-----------|--------------|------------|---------|-------------------------------------------------------|------------------------------|
|     1 | euna20104 | BMIWS        | 6.2.x      | APEU201 | EUNA20104                                             | Push                         |
|     2 | euna20106 | RINA         | 6.2.x      | APEU201 | EUNA20106                                             | pull                         |
|     3 | euna20110 | RINA         | 6.2.x      | APEU201 | EUNA20110, EUNA20111, EUNA20112, EUNA20113, EUNA20114 | pull                         |
|     4 | euna20204 | BMIWS        | 6.2.x      | APEU202 | EUNA20204                                             | pull                         |
|     5 | euna20206 | RINA         | 6.2.x      | APEU202 | EUNA20206                                             | push                         |
|     6 | euna20207 | RINA         | 6.2.x      | APEU202 | EUNA202047                                            | push                         |
|     7 | euna20210 | RINA         | 6.2.x      | APEU202 | EUNA20210, EUNA20211, EUNA20212, EUNA20213, EUNA20214 | push                         |

<!-- image -->

All Windows servers are installed as Standard B8ms as defined by Microsoft Azure and have 8vCPU, 32 GB RAM and a 128GB SSD drive.

## 2.1.2 Scope of L2 environment and tests

The  main scope  of  L2  environment  is  to  check  the  functionality  of  the  EESSI components , meaning CSN, AP and RINA, and the basic integration between them.

In L2 environment, the upgrade installation is not used and all components have clean complete installs. For RINA only Windows installations are used at this level.

Main activities in L2 environments:

- Execute bugs regression and check all bug fixes
- Execute  functional  test  suites  for  all  components,  manual  and  automated,  at  all interfaces level:
- o UI
- o CPI
- o BMI
- o NIE
- Execute integration tests between components.

In order to have a high coverage of RINA configurations tests, different configurations are used. For different RINA installations, different configuration parameters are used, such as:

- SSL: ON / OFF
- Transport mode: PUSH/ PULL
- BMI only machines
- Tenants: Single /multi - tenant machines
- Integration with eTranslation
- Integration with one predefined AD server to check directory services integrations

Note: The interoperability testing of RINA 6.2.x versions is performed against RINA 5.6.4 only.

## 2.2 L3 Continuous Delivery environment

## 2.2.1 Overview

The L3 CD environment consists of one CSN server, four AP servers and nine RINA servers. The servers and their role in the testing environment are described on the following table:

<!-- image -->

<!-- image -->

|   No. | Name       | Component   | Version   | AP      | Tenant                                                                     | Transport Mode (Push/Pull)   |
|-------|------------|-------------|-----------|---------|----------------------------------------------------------------------------|------------------------------|
|     1 | euna30104  | BMIWS       | 6.2.x     | APEU301 | EUNA30104                                                                  | pull                         |
|     2 | euna30106  | RINA        | 6.2.x     | APEU301 | EUNA30106                                                                  | push                         |
|     3 | euna30110  | RINA        | 6.2.x     | APEU301 | EUNA30110, EUNA30111, EUNA30112, EUNA30113, EUNA30114, … up to 100 tenants | pull                         |
|     4 | euna302100 | RINA        | 6.2.x     | APEU302 | EUNA302100                                                                 | push                         |
|     5 | euna303100 | RINA        | 5.6.x     | APEU303 | EUNA303100                                                                 | push                         |
|     6 | euna30404  | BMIWS       | 6.2.x     | APEU304 | EUNA30404                                                                  | pull                         |
|     7 | euna30405  | RINA        | 6.2.x     | APEU304 | EUNA30405                                                                  | push                         |
|     8 | euna30407  | RINA        | 6.2.x     | APEU304 | EUNA30407                                                                  | pull                         |
|     9 | euna30410  | RINA        | 6.2.x     | APEU304 | EUNA30410, EUNA30411 , … up to 100 tenants                                 | push                         |

All  Windows and Linux servers are installed as Standard B8ms as defined by Microsoft Azure and have 8vCPU, 32 GB RAM and a 128GB SSD drive.

## 2.2.2 Scope of L3 Environment and Tests

The  main scope  of  L3  environment  is  to  check  the  functionality  of  the  EESSI components  in  multiple  configurations,  execute  load  and  performance  tests ,

<!-- image -->

meaning CSN, AP and RINA, and basic integration  between  these  components  in  load conditions.

In L3 most of the installations are in upgrade mode, to allow for testing of the upgrade procedures. In L3 environment, the High Performance and High Availability configurations are also covered together with standalone installations. (Note that upgrades and multiple node deployments are currently not handled by the CI platform).

The main testing activities in L3 environments are:

- Execute bugs regression and check all bug fixes. Review specific bugs to L3 tests, such as upgrade bugs, different OS dependent bugs, load bugs etc.
- Run tests scenarios specific to upgrade operations.
- The tests executed include a part of functional tests done in L2.
- Execute performance and load tests.
- Execute integration tests between components: in this environment an older RINA installation is used to check interoperability with previous versions.

## 2.3 PL Continuous Delivery environment

## 2.3.1 Overview

The PL CD environment consists of one CSN server, four AP servers and thirteen RINA servers. Below there is a table with all the servers and their roles in PL testing environment:

<!-- image -->

<!-- image -->

|   No. | Name       | Component   | Versio n   | AP      | Tenant                                                            | Tranport Mode (Push/Pull)   |
|-------|------------|-------------|------------|---------|-------------------------------------------------------------------|-----------------------------|
|     1 | eunapl104  | BMIWS       | 5.6.2      | APEUPL1 | EUNAPL104                                                         | pull                        |
|     2 | eunapl105  | BMIWS       | 5.6.2      | APEUPL1 | EUNAPL105                                                         | pull                        |
|     3 | eunapl106a | RINA        | 5.6.4      | APEUPL1 | EUNAPL106A                                                        | pull                        |
|     4 | eunapl106b | RINA        | 5.6.4      | APEUPL1 | EUNAPL106B                                                        | pull                        |
|     5 | eunapl106c | RINA        | 5.6.4      | APEUPL1 | EUNAPL106C                                                        | pull                        |
|     6 | eunapl206  | RINA        | 5.6.2      | APEUPL2 | EUNAPL206                                                         | push                        |
|     7 | eunapl207  | RINA        | 5.6.2      | APEUPL2 | EUNAPL207                                                         | pull                        |
|     8 | eunapl210  | RINA        | 5.6.2      | APEUPL2 | EUNAPL210, EUNAPL211, EUNAPL212, EUNAPL213, EUNAPL214, EUNAPL215. | Push                        |
|     9 | eunapl306  | RINA        | 5.6.4      | APEUPL3 | EUNAPL306                                                         | pull                        |
|    10 | eunapl307  | RINA        | 5.6.4      | APEUPL3 | EUNAPL307 (BUC set 1)                                             | push                        |
|    11 | eunapl310  | RINA        | 5.6.4      | APEUPL3 | EUNAPL307 (BUC set 2), EUNAPL311, EUNAPL312, EUNAPL313            | push                        |
|    12 | eunapl406  | RINA        | 5.6.4      | APEUPL4 | EUNAPL406                                                         | pull                        |
|    13 | eunapl407  | RINA        | 5.6.4      | APEUPL4 | EUNAPL407                                                         | push                        |

All  Windows and Linux servers are installed as Standard B8ms as defined by Microsoft Azure and have 8vCPU, 32 GB RAM and a 128GB SSD drive.

## 2.3.2 Scope of Production-like (PL) environment and Tests

The main objectives of PL1 environment are:

- To have a replica at a small scale of a production environment, in order to be able to check and establish reproduction conditions for production bugs.
- To check the interoperability between current productions versions and new versions.
- To  check  adequate  operation  of  new  versions  with  old  model  versions (adequate handling of model 4.1 cases).
- Check migration procedures from RINA 2019 to RINA 2020 versions, for BMI and full stack.

In PL1 most of the installations are in upgrade mode, to allow for testing of the upgrade procedures. All the installations are done manually using the installation guides, in order to also check guides adequacy.

Main activities executed in these environments are:

- Bugs checking and localization for bugs received from production.
- The tests executed include a part of functional tests done in L2/L3 and more tests especially regarding checking of upgrade /migrations of data.
- Execute verifications specific to cases with data from old models (4.1).
- Execute specific tests for model upgrades.

## 3 EESSI Continuous infrastructure deployment

## 3.1 Overview

All  the  testing  infrastructure  is  deployed  in  the  Microsoft  Azure  environment  using  an infrastructure as code tool called Terraform. Current Terraform version used is v0.13.3 with Azure provider version 2.20.0. You can find more information about Terraform at the following URL - https://www.terraform.io/.

Terraform configuration files are kept in the project's version control system Git so all the team members can access and use the latest version of the infrastructure configuration files.  Terraform  state  files  are  also  stored  in  a  central  accessible  location,  in  Microsoft Azure.

Note : Configuration files for L2/L3/PL are located under pr oject ' terraform-scripts '. This shall not to be confused with the similarly named /scripts/terraform in the ' jenkins-jobs ' project (which manages the CI platform and L1 deployments).

## 3.2 EESSI CD infrastructure deployment configuration

All CD environments are using the same Terraform configuration files described below. For each environment, the input data is unique to the environment and is modified accordingly to the environment needs.

- The folder structure with configuration files is presented below:

<!-- image -->

<!-- image -->

## Delivery Environments

<!-- image -->

- Folders L2, L3 and PL are specific to each environment in EESSI CD infrastructure. They contain configuration files with input data corresponding to each environment.
- Folder \_modules is shared between L2, L3 and PL environment's configurations. This folder  contains  modules  that  represent  configuration  files  about  how  to  create different objects for our EESSI CD infrastructure in Microsoft Azure. The modules here describe how to create Virtual Machine (VM) resources for our environment, and they  are  called  through  the  main.tf  configuration  file  in  the  configuration  folder specific to each environment. Below is a picture with all the modules used and their files:
- o rina\_l\_deploy\_01 module contains configuration files that instruct Terraform on how to create Ubuntu 16.04-LTS Virtual Machines that will be later  used  to deploy RINA software:
- instance.tf is the main file of the module with instructions on how to create the virtual machines running on Ubuntu 16.04-LTS
- variables.tf declares variables used by this module
- network.tf instruct Terraform on how to create the Network Interface Card and the Public IP Address for the Ubuntu 16.04-LTS Virtual Machines
- o rina\_l\_deploy\_02 module contains configuration files that instruct Terraform on how to create Ubuntu 18.04-LTS Virtual Machines that will be later  used  to deploy RINA software:
- instance.tf is the main file of the module with instructions on how to create the virtual machines running on Ubuntu 18.04-LTS
- variables.tf declares variables used by this module
- network.tf instruct Terraform on how to create the Network Interface Card and the Public IP Address for the Ubuntu 18.04-LTS Virtual Machines
- o rina\_w\_deploy\_01 module contains configuration files that instruct Terraform on how to create Windows Server 2016 Datacenter Virtual Machines that will be later used to deploy RINA software:
- instance.tf is the main file of the module with instructions on how to create the virtual machines running Windows Server 2016 Datacenter
- variables.tf declares variables used by this module

<!-- image -->

▪

network.tf instruct Terraform on how to create the Network Interface Card

and the Public IP Address for Virtual Machines

- o scripts is a folder containing any scripts the Terraform is running towards the Virtual  Machines  it  creates.  Currently  it  contains  a  PowerShell  script  that enables  WinRM  on  the  Windows  Server  2016  Datacenter  Virtual  Machines created by Terraform.

<!-- image -->

## 3.3 L2 infrastructure deployment configuration files

EESSI  CD  L2  testing  environment  is  using  the  Terraform  configuration  files  described below.  The  input  data  is  modified  corresponding  to  the  environment  needs.  L2  Folder contains configuration files that instruct Terraform on how to create Azure objects for the L2 EESSI CD environment:

<!-- image -->

- variables.tf declares variables used by this module
- provider.tf defines the Terraform Microsoft Azure provider version used
- L2-backend.tf specifies that the Terraform state for the environment it creates/manages is stored in a Microsoft Azure storage container, in a file named L2, in a folder named tfstate
- main.tf defines what Terraform modules to be used by this environment.
- Readme.md contains instructions on how to use the Terraform configuration files for this environment.
- L2-integration.tfvars is the input file for this environment. Here we are defining what Microsoft  Azure  Resource  Group  to  create,  what  Virtual  Network  and  its  Virtual Subnets and what Virtual Machines to be created.
- The  subfolder ' vm\_modules"  contains  the  subfolder  rsg  that  defines  how  the Microsoft Azure Resource Group for the L2 EESSI CD environment will be created, how Virtual Networks and how Virtual Subnets will be created. It also defines what firewall rules are created for the L2 environment in Microsoft Azure and what DNS servers to be used in the environment.

<!-- image -->

<!-- image -->

## 3.4 L3 infrastructure deployment configuration files

EESSI CD L3 testing environment is  using identical Terraform configuration files as L2 environment  except  the  following  described  input  files  that  are  different  from  the corresponding ones in L2 environment:

- L3-backend.tf specifies that the Terraform state for the environment it creates/manages is stored in a Microsoft Azure storage container, in a file named L3, in a folder named tfstate;
- L3-integration.tfvars is the input file for this environment. This file is used to define the  following:  (i)  the  Microsoft  Azure  Resource  Group  to  create,  (ii)  the  Virtual Network and its Virtual Subnets and (iii) the Virtual Machines to be created;
- The subfolder vm\_modules contains the subfolder rsg that defines how Microsoft Azure Resource Group for the L3 EESSI CD environment will be created, how Virtual Networks and how Virtual Subnets will be created. It also defines what firewall rules are created for the L3 environment in Microsoft Azure and what DNS servers to be used in the environment.

## 3.5 PL infrastructure deployment configuration files

EESSI CD LP testing environments is using identical Terraform configuration files as the L2 environment. The only files that are different are the input files described below:

<!-- image -->

- PL-backend.tf specifies that the Terraform state for the environment it creates/manages is stored in a Microsoft Azure storage container, in a file named PL, in a folder named tfstate
- PL-integration.tfvars is the input file for this environment. Here we are defining what Microsoft  Azure  Resource  Group  to  create,  what  Virtual  Network  and  its  Virtual Subnets and what Virtual Machines to be created.

The subfolder vm\_modules contains the subfolder rsg that defines how Microsoft Azure Resource Group for the PL EESSI CD environment will be created, how Virtual Networks and how Virtual Subnets will be created. It also defines what firewall rules are created for the  PL  environment  in  Microsoft  Azure  and  what  DNS  servers  to  be  used  in  the environment.

<!-- image -->

## 4 EESSI Continuous Delivery Environments applications deployment

All  the  systems  under  test  are  deployed  on  the  virtual  machines  consisting  the infrastructure environment in Microsoft Azure using scripts and/or manual steps. All the Bash, PowerShell, Python and Ansible scripts are sto red in the EESSI project's version control system, Git.

The description of the scripts that can be used for automatic configuration of RINA can be found in the document ' EESSI -RINA -Continuous Integration Environments (Layer 1) ' -[R1], and in the scripts provided in the folder 'scripts' in the 'Jenkins -jobs' repository.