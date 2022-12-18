
## Migrate Certain Tables from ONPREM Database using DMS into Apache Hudi Transaction Datalake with Glue

![dynamodbstreams drawio (1)](https://user-images.githubusercontent.com/39345855/208271941-4c780610-3a8d-455b-8fbe-c00c5a5dcc11.png)


#### Helpful Resources 
* https://docs.aws.amazon.com/dms/latest/userguide/CHAP_Source.PostgreSQL.html


* NOTE if you want to anble incremental data processing on Glue side you can simply add bookmark while reading data from catlog 

```
AWSGlueDataCatalog_node1670351852970 = glueContext.create_dynamic_frame.from_catalog(
    database="XXXXXX",
    table_name="XXXXX",
    transformation_ctx="AWSGlueDataCatalog_node1670351852970",
    additional_options={"jobBookmarkKeys": ["<UNIQUE KEY >"], "jobBookmarkKeysSortOrder": "asc"},
)
```
