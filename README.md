#PDI ODM CE
======================

PDI Operations Mart CE is a free and open source projetc. <BR>
It is available under the terms of the Apache License Version 2.<BR>
Version: 1.2<BR>
License: Apache License Version 2<BR>

#How to install:

1) Open pgAdmin3 and create a database called pdi_odm_ce;

```
CREATE DATABASE pdi_odm_ce;
```

2) Run the DDL Script ddls-pdi-odm-ce.sql on pgAdmin3 to create the logs schema and all the tables;

3) Edit your kettle.properties file (/Users/caiomsouza/.kettle/kettle.properties) and add the lines below:

```
PDI_ODM_CE_HOST=localhost <BR>
PDI_ODM_CE_DATABASE=pdi_odm_ce <BR>
PDI_ODM_CE_PORT=5432<BR>
PDI_ODM_CE_USERNAME=YOUR_USER<BR>
PDI_ODM_CE_PASSWORD=YOUR_PASSWORD<BR>
LOG_CONNECTION=pdi_odm_ce<BR>
LOG_SCHEMA=logs<BR>
LOG_T=log_transformation<BR>
LOG_S=log_step<BR>
LOG_P=log_performance<BR>
LOG_LC=log_logging_channels<BR>
LOG_M=log_metrics<BR>
```

Windows:<BR>
C:\Documents and Settings\<username>\.kettle\kettle.properties<BR>
Linux:<BR>
/Users/<username>/.kettle/kettle.properties<BR>

(See https://github.com/it4biz/pdi-odm-ce/blob/master/kettle.properties)<BR>

4) Put the file pdi_odm_ce.kdb (DB Connection) on your Kettle file repository and change the variables PDI_ODM_CE_USERNAME and  PDI_ODM_CE_PASSWORD

5) Open the example transformation (t_it4biz_standard_transformation_with_log_enable.ktr) and run it.

6) Go to pgAdmin3 and see the results on the tables:

```
logs.log_transformation<BR>
logs.log_step<BR>
logs.log_performance<BR>
logs.log_logging_channels<BR>
logs.log_metrics<BR>
```

7) Fork it and make your own contribution.

We need help to create a Data mart, an OLAP Mondrian Schema Cube and some Reports/Dashboards to help to visualize the logs data in a better way than SQL Queries. 

#To learn more about this subjetc:
http://infocenter.pentaho.com/help48/index.jsp?topic=%2Fpdi_admin_guide%2Fconcept_pdi_operations_mart.html

#Contributions:
5 (five) PRD Reports - Fabio de Salles <fabio.salles@globo.com> - 11/Dec/2014

