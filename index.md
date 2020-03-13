# github pages

除此之外，也可以通过访问 TiDB 提供的 HTTP 接口查看当前 owner 所在 TiDB，以及各个 TiDB 节点 `ddl_id`、`lease` 等信息，用法如下：

```shell script
# 用法
curl http://{TiDBIP}:10080/info/all
# 例如
$curl http://127.0.0.1:10080/info/all
{
    "servers_num": 2,
    "owner_id": "29a65ec0-d931-4f9e-a212-338eaeffab96",
    "is_all_server_version_consistent": true,
    "all_servers_info": {
        "29a65ec0-d931-4f9e-a212-338eaeffab96": {
            "version": "5.7.25-TiDB-v4.0.0-alpha-669-g8f2a09a52-dirty",
            "git_hash": "8f2a09a52fdcaf9d9bfd775d2c6023f363dc121e",
            "ddl_id": "29a65ec0-d931-4f9e-a212-338eaeffab96",
            "ip": "",
            "listening_port": 4000,
            "status_port": 10080,
            "lease": "45s",
            "binlog_status": "Off"
        },
        "cd13c9eb-c3ee-4887-af9b-e64f3162d92c": {
        "version": "5.7.25-TiDB-v4.0.0-alpha-669-g8f2a09a52-dirty",
        "git_hash": "8f2a09a52fdcaf9d9bfd775d2c6023f363dc121e",
        "ddl_id": "cd13c9eb-c3ee-4887-af9b-e64f3162d92c",
        "ip": "",
        "listening_port": 4001,
        "status_port": 10081,
        "lease": "45s",
        "binlog_status": "Off"
        }
    }
}
```

### 7.2.3 DDL 相关参数
#### 参数
* `tidb_ddl_reorg_worker_cnt`
