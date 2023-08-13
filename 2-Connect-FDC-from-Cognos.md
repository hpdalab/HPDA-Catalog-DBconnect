
# Connect to Fusion Data Catalog from Cognos Analytics Server


## Reference 

## Install Cognos Analytics Server


#### Launch the Installer on Windows

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/4dcfbbfa-ac3a-47d6-bf45-4859edab9a82)


#### Select Installation Location

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/1d518a67-ea76-4fec-9113-2eeef32eae5a)


#### Choose Easy Install

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/6464c825-1842-4643-a370-b9371bb1f991)


#### Create Admin Credential

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/7b32b44e-697f-4916-b08e-aadf35c5b761)


#### Installing

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/4fc6475a-ae3c-45f7-a1d8-caedfd26594a)


#### Installation Completed

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/69437c0f-f637-4892-8b54-a3ef9eefe1b0)


## Configure Cognos Analytics Server

#### Open Cognos Configurator

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/a557dbaf-d151-4ad4-99e5-e68f1e015988)

#### Start to configure

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/08961aad-507e-417e-bcc7-c56eb44f0daa)


## Add Presto Drivers to Cognos

Download both presto drivers: 1) "presto-cli-0.282-executable.jar" from https://repo1.maven.org/maven2/com/facebook/presto/presto-cli/0.282/presto-cli-0.282-executable.jar and 2) "presto-jdbc-0.282.jar" from https://repo1.maven.org/maven2/com/facebook/presto/presto-jdbc/0.282/presto-jdbc-0.282.jar, and place them in the Cognos Analytics Drivers folder

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/2883a4df-bdad-4547-a531-f9772b485b40)

Restart the Cognos Analytics using Configurator


## Connect to WXD with Cognos Data Server

#### Log into Cognos Analytics

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/d431d0c8-da73-49a0-b86a-df30e4901b0b)

#### Set up Data server connections

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/084d22db-fc81-4cda-ab3a-1f54e3d3317f)

#### Enter FDC100 parameters into Connection Tab
```
JDBC URL: jdbc:db2://********-us-south.lb.appdomain.cloud:50000/BLUDB
Driver Class Name: com.ibm.db2.jcc.DB2Driver
Authentication Method: use signon (enter user name and password)
```

<img width="1245" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/8ba5f8a2-193e-4dfc-941a-e5639d937eb4">


#### Test connection to FDC100

<img width="1164" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/d526dac1-3dd9-4d6a-b58e-5bd28239d80f">

#### In Action Menu, click Assets

<img width="1178" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/6c0f0e9e-7e2f-43d6-bdd4-09a3c24a1eff">

#### Review Schemas from FDC100 and load tables from Schema Bluadmin

<img width="1166" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/79ae32f3-ac4b-4f73-9f0f-2a2d7f9872cb">


## Create Cognos Data Module

#### In main menu, select + New then Data Module

<img width="1190" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/0132bb5e-8f1c-4ceb-afd5-d9805cbf222f">

#### Select FDC100 from Data Server & Schemas 

<img width="962" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/9de0aa65-d343-4b58-8e37-8d441c2b67d1">

#### Select Schema BLUADMIN

<img width="963" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/6ab16529-3193-4ae3-bedc-1c29665991b7">


#### Pick "Select Table"

<img width="965" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/a75cc4ec-881c-406b-be75-d751d8fc43ef">


#### Pick Table "metaocean"

<img width="965" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/6010cb61-2054-491e-9b82-bd818aa0cc67">

#### Data Populated in Table

<img width="965" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/1c9b50e1-a08e-4f4a-bf85-4aa6dc291c99">

#### Voew Data from FDC100 in Data Module

<img width="1187" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/f30dc695-92e1-4474-8291-a6052ea25341">











