# oraclepaas

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "oraclepaas" {
  version = "1.5.3"

  # application_endpoint - (optional) is a type of string
  application_endpoint = null
  # database_endpoint - (optional) is a type of string
  database_endpoint = null
  # identity_domain - (required) is a type of string
  identity_domain = null
  # insecure - (optional) is a type of bool
  insecure = null
  # java_endpoint - (optional) is a type of string
  java_endpoint = null
  # max_retries - (optional) is a type of number
  max_retries = null
  # mysql_endpoint - (optional) is a type of string
  mysql_endpoint = null
  # password - (required) is a type of string
  password = null
  # user - (required) is a type of string
  user = null
}
```

[top](#index)

### Resources


- [oraclepaas_application_container](./r/oraclepaas_application_container.md)

- [oraclepaas_database_access_rule](./r/oraclepaas_database_access_rule.md)

- [oraclepaas_database_service_instance](./r/oraclepaas_database_service_instance.md)

- [oraclepaas_java_access_rule](./r/oraclepaas_java_access_rule.md)

- [oraclepaas_java_service_instance](./r/oraclepaas_java_service_instance.md)

- [oraclepaas_mysql_access_rule](./r/oraclepaas_mysql_access_rule.md)

- [oraclepaas_mysql_service_instance](./r/oraclepaas_mysql_service_instance.md)


[top](#index)

### Datasources


- [oraclepaas_database_service_instance](./d/oraclepaas_database_service_instance.md)


[top](#index)