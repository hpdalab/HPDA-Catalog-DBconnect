# Connect to Fusion Data Catalog with Eclipse BIRT


## Reference:
1. DB2 JDBC Driver Downlaod: https://mvnrepository.com/artifact/com.ibm.db2.jcc/db2jcc
2. 18 Free and Open Source BI Tools: https://logz.io/blog/business-intelligence-tools/
3. Presto JDBC Driver: https://prestodb.io/getting-started.html (Parameter: https://prestodb.io/docs/current/installation/jdbc.html)
4. Eclipse BIRT Project: https://eclipse-birt.github.io/birt-website/
5. Design BIRT Reports on Presto Data (cdata): https://www.cdata.com/kb/tech/presto-jdbc-birt.rst
6. Blog - BIRT SQL Server JDBC Driver Explained: https://bobcares.com/blog/birt-sql-server-jdbc-driver/
7. Tutorial - https://www.youtube.com/watch?v=Dxjq99Sl5bM


## Install Elcipse-BIRT on PC

#### Visit Elipse-Birt Github 

Go to https://eclipse-birt.github.io/birt-website/ 

<img width="1247" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/d97fb4e1-1f77-4215-a988-7bc4d0ea074f">


#### Select Windows package to download

"birt-report-designer-all-in-one-4.13.0-20230302-win32.win32.x86_64.zip" 

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/0e1bd8de-6b4e-425e-b23e-7c7fdd347500)


#### Extract the zip file

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/8b2c8cd3-8142-444b-89da-3ee5edce5b2c)


## Launch Eclipse with New BIRT Project

#### Launch Eclipse from the installation folder

From the File menu, select New Project. In the popped-up wizard, select Business Intelligence and Reporting Tools and then Report Project

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/1d47409a-c813-4eac-9f58-55e71aa8d583)

#### Create project

After naming and selecing the location for the project "BRT100-prj001-test", open perspective

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/fa823437-ab99-45ad-aec7-ed32a3615b16)


#### Workspace perspective will open

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/1c92fb7e-136f-4773-b14b-ad5882dc07b7)


## Load Sample Template

#### From menu, open File - New - Other

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/d13af7ba-c747-44a7-8689-59c1e0fcfb7c)

#### In Select a wizard, pick BIRT - Report then Next

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/c4c75c00-ba25-4b20-a981-07950c7097df)

#### Select the current project "BRT100-prj001-test", cliick Next

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/b4d19a8b-62e3-4ec6-b940-89e20deff407)

#### Select a report template from the Standard

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/d917d273-31b5-4ccd-8f61-83d888e1e775)


#### Return to the Perspective with the template "My First Report" loaded

![image](https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/41b87016-cae7-4d6d-a24d-6081b72a8fd5)


## Connect to Fusion Data Catalog (FDC100)

#### Add Db2 JDBC Driver to Elipse 

```
Source of DB2 JDBC Driver: https://mvnrepository.com/artifact/com.ibm.db2.jcc/db2jcc
Elcipse Driver Folder: \eclipse\plugins\org.eclipse.birt.report.data.oda.jdbc_4.13.0.v202303021806
Driver JAR File Name: db2jcc-db2jcc4
Driver Class Name: com.ibm.db2.jcc.DB2Driver
```
<img width="751" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/ee22ca8a-a52d-45b3-893d-c82859c45320">

#### Create New JDBC Data Source

<img width="426" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/cf307acf-aeb4-4247-bc37-3854237be302">

#### Add Driver & Parameters for FDC100

<img width="805" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/ccaf58e1-a97d-469f-8a9a-c121ed80c309">

```
Driver Class: com.ibm.db2.jcc.DB2Driver ( v4.25)
Database URL: jdbc:db2://******-us-south.lb.appdomain.cloud:50000/BLUDB
User Name: bluadmin
Password: ******
JNDI URL: left blank
```

## Create New Data Set

#### Right Click on Data Set to Create New "BRT100-dataset001-fdc100"

<img width="425" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/b210ad30-f82d-43ea-92a9-37a29fdc8dcf">

#### Query Table Opens

<img width="648" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/68504c7a-6048-4d67-8b50-025e3f0d6b6f">

#### Build Query in Dataset
```
select *
from BLUADMIN.METAOCEAN
where TAG1 = "dat.breakhis.T100140.R2"
```
<img width="1291" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/45587ccc-4cde-4b62-90f6-baa2a7a74836">

Preview Results

<img width="1218" alt="image" src="https://github.com/hpdalab/FusionDataCatalog-Connect/assets/38366661/0f032420-e081-4452-8352-83ab9903a5c8">






