![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/a6cb8bc1-8b4f-47f2-a9cc-fa9d818761c7)![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/57a6510b-8569-4d22-99e8-fe27560010a6)# Connect Fusion Data Cataloging (FD100C) from watsonx.data (WXD100)


## Reference:
1. WXD100 (watsonx.data deployed in Fusion101 Cluster)


## Log into WXD100

#### Landing Page

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/957cab46-cd55-4bb0-9b49-1e92e68a5571)


![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/8ce9f4cb-5533-42f2-ad1d-41e258b9bb6c)

#### Open Lakehouse Instance

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/cf5a2286-5442-4c99-8329-33f54f7b340a)


#### watsonx.data (WXD100) Landing Page

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/0e01a192-7acf-4b92-b489-373115b54206)


## Work with Infrastructure Manager

#### Open Infrastructure Manager to Add Database

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/2220a776-d2e7-41f1-9fbb-852f6198a87f)


#### Add FDC100 as Database and Catalog

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/d792d8af-871f-450f-80df-951ab5925afa)


#### View Connected DB2 and Catalog in Infrastructure Manager

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/87172eff-dd44-46f4-a925-6a07db47e8c3)


#### View Detail of Database

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/e1899eba-37ac-4f49-8bd2-e1fd88a394e0)


## Work with Connected FDC100 Schema/Table in Data Manager

#### Select presto-01 Engine and navigate to "fusion101fdc" Catalog

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/955f6bc6-2b9d-4ac6-b924-8838681ba141)

#### Pick to open blueadmin schema and navigate to "metaocean" table

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/b7b9e93e-4c73-4ad8-9a59-51af23192089)


#### Browse the Table Schema

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/3ba1f453-9dcf-4ca3-82ee-cea2572063cb)


#### Browse the Data Sample

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/f2f51f9e-d381-41ca-a708-c7acd708fd7d)


#### Browse DDL 

```
CREATE TABLE fusion101fdc.bluadmin.metaocean (
   "datasource" varchar(1024) NOT NULL,
   "operation" varchar(64),
   "ingesttype" varchar(12),
   "revision" varchar(4),
   "site" varchar(16),
   "platform" varchar(32),
   "cluster" varchar(64) NOT NULL,
   "inode" bigint NOT NULL,
   "owner" varchar(32),
   "group" varchar(64),
   "permissions" varchar(10),
   "fileset" varchar(1024),
   "uid" bigint,
   "gid" bigint,
   "path" varchar(4096),
   "filename" varchar(1024),
   "filetype" varchar(256),
   "recordversion" varchar(64),
   "state" varchar(8),
   "migloc" varchar(256),
   "mtime" timestamp,
   "atime" timestamp,
   "ctime" timestamp,
   "inserttime" timestamp,
   "updatedtime" timestamp,
   "requesttime" timestamp,
   "scangen" bigint,
   "tier" varchar(16),
   "size" bigint,
   "qpart" smallint,
   "fkey" varchar(2048) NOT NULL,
   "collection" varchar(256),
   "temperature" varchar(256),
   "duplicate" varchar(256),
   "tag1" varchar(256),
   "tag2" varchar(256),
   "tag3" varchar(256),
   "tag4" varchar(256),
   "tag5" varchar(256),
   "tag6" varchar(256),
   "tag7" varchar(256),
   "tag8" varchar(256),
   "tag9" varchar(256),
   "tag10" varchar(256),
   "tag11" varchar(256),
   "tag12" varchar(256),
   "tag13" varchar(256),
   "tag14" varchar(256),
   "tag15" varchar(256),
   "tag16" varchar(256),
   "sizeconsumed" bigint
)
```

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/e7180e09-6146-4dac-bf68-ce784ccd25c0)


## Work with Connected FDC100 Schema/Table in Query Workspace


#### Run SQL query to retrieve dataset "dat.salento.T102229.R3"

```
select * from fusion101fdc.bluadmin.metaocean 
where datasource='fusion101' and tag1='dat.salento.T102229.R3'
```

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/8065a403-b70a-4b5f-9e6b-0b0929c8701d)


#### Run SQL query to export the retrieved dataset to table

```
create table bkt003c1.bkt003_fdc100.bkt003_fdc100_salentoR3
WITH (
  format = 'orc'
)
as 
select * from fusion101fdc.bluadmin.metaocean 
where datasource='fusion101' 
and tag1='dat.salento.T102229.R3'
```

![image](https://github.com/hpdalab/lab100.FDC100-DBconnect/assets/38366661/b49540f9-915f-4c45-8741-48a723f7ad32)

#### View table "bkt003c1.bkt003_fdc100.bkt003_fdc100_salentoR3" in Data Manager

![image](https://github.com/hpdalab/lab100.FDC-DBconnect/assets/38366661/703f21f3-b17a-42d1-b64e-601139ff4b51)

