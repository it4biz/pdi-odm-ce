pdi-operations-mart-ce
======================

PDI Operations Data mart CE

How to install:

1) Open pgAdmin3 and create a database called pdi_odm_ce;

CREATE DATABASE pdi_odm_ce

2) Run the DDL Script ddls-logs-transformations.sql on pgAdmin3 to create the logs schema and all the tables;

3) Edit your kettle.properties file (/Users/caiomsouza/.kettle/kettle.properties) and add the lines below:

# PDI Operations Mart CE
#PDI ODM CE
PDI_ODM_CE_HOST=localhost
PDI_ODM_CE_DATABASE=pdi_odm_ce
PDI_ODM_CE_PORT=5432
PDI_ODM_CE_USERNAME=YOUR_USER
PDI_ODM_CE_PASSWORD=YOUR_PASSWORD
#LOGs Tables
LOG_CONNECTION=curso_pdi_sp_nov14
LOG_SCHEMA=logs
LOG_T=log_transformation
LOG_S=log_step
LOG_P=log_performance
LOG_LC=log_logging_channels
LOG_M=log_metrics

4) Put the file pdi_odm_ce.kdb (DB Connection) on your Kettle file repository and change the variables PDI_ODM_CE_USERNAME and  PDI_ODM_CE_PASSWORD

5) Open the example transformation (t_it4biz_standard_transformation_with_log_enable.ktr) and run it.

6) Go to pgAdmin3 and see the results on the tables:

logs.log_transformation
logs.log_step
logs.log_performance
logs.log_logging_channels
logs.log_metrics

7) Fork it and make your own contribution.

We need help to create a Data mart, an OLAP Mondrian Schema Cube and some Reports/Dashboards to help to visualize the logs data in a better way than SQL Queries. 

To learn more about this subjetc:
http://infocenter.pentaho.com/help48/index.jsp?topic=%2Fpdi_admin_guide%2Fconcept_pdi_operations_mart.html
