# ansible-inventory command example

`ansible-inventory  -i hosts.yaml --export  --list`

```json
{
    "_meta": {
        "hostvars": {}
    },
    "all": {
        "children": [
            "nacos-template-config",
            "ungrouped"
        ],
        "vars": {
            "mysql_db_name": "globaldb",
            "mysql_db_pass": {
                "__ansible_vault": "$ANSIBLE_VAULT;1.1;AES256\n62313365396662343061393464336163383764373764613633653634306231386433626436623361\n6134333665353966363534333632666535333761666131620a663537646436643839616531643561\n63396265333966386166373632626539326166353965363262633030333630313338646335303630\n3438626666666137650a353638643435666633633964366338633066623234616432373231333331\n6564\n"
            },
            "mysql_db_username": "demo",
            "mysql_jdbc_url": "jdbc:mysql://127.0.0.1:3306/test",
            "server": {
                "grpc": 9098,
                "port": 8080
            },
            "toggle": {
                "loginV2": true,
                "saveNas": true
            }
        }
    },
    "nacos-template-config": {
        "hosts": [
            "127.0.0.1"
        ],
        "vars": {
            "demo_json_config": {
                "content": "{\n    \"mysql-username\" : \"{{ mysql_db_username }}\",\n    \"password\" : \"foot\"\n}\n",
                "format": "json",
                "name": "demo.json"
            },
            "demo_properties_config": {
                "config": "server.port = 9090\nspring.application.name = demoservice",
                "format": "properties",
                "name": "demo.properties"
            },
            "demo_yaml_config": {
                "content": "spring:\n   application:\n      name: demoservice\n   server:\nport: 9090",
                "format": "yaml",
                "name": "demo.yaml"
            }
        }
    }
}
```
