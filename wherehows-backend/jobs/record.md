azkaban_execution

1、添加app/database, id与job配置job.ref.id 一致


curl -X POST \
  http://ip:9001/cfg/app \
  -H 'content-type: application/json' \
  -d '{
      "app_id": 14,
      "app_code": "azkaban_execution",
      "description": "azkaban_execution",
      "parent_app_id": 0,
      "app_status": "A",
      "uri": "http://ip:9000/",
      "short_connection_string": "azkaban-execution"
    }'
    
 
curl -X POST \
  http://ip:9001/cfg/db \
  -H 'content-type: application/json' \
  -d '{
      "db_id": 65,
      "db_code": "hive_sqldb",
      "description":"hive mysql db",
      "primary_dataset_type":"hive",
      "associated_dc_num":1,
      "cluster_size": 2,
      "associated_data_centers": 1,
      "replication_role": "MASTER",
      "uri": "http://hive",
      "short_connection_string": "hive-metadata"
    }'
    
2、UMP_METRIC_ETL.job 对应的py，没有

3、Git 相关表未使用，停留在单元测试

