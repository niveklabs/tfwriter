# vault_database_secret_backend_connection

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.17.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_database_secret_backend_connection" {
  source = "./modules/vault/r/vault_database_secret_backend_connection"

  # allowed_roles - (optional) is a type of list of string
  allowed_roles = []
  # backend - (required) is a type of string
  backend = null
  # data - (optional) is a type of map of string
  data = {}
  # name - (required) is a type of string
  name = null
  # root_rotation_statements - (optional) is a type of list of string
  root_rotation_statements = []
  # verify_connection - (optional) is a type of bool
  verify_connection = null

  cassandra = [{
    connect_timeout  = null
    hosts            = []
    insecure_tls     = null
    password         = null
    pem_bundle       = null
    pem_json         = null
    port             = null
    protocol_version = null
    tls              = null
    username         = null
  }]

  elasticsearch = [{
    password = null
    url      = null
    username = null
  }]

  hana = [{
    connection_url          = null
    max_connection_lifetime = null
    max_idle_connections    = null
    max_open_connections    = null
  }]

  mongodb = [{
    connection_url          = null
    max_connection_lifetime = null
    max_idle_connections    = null
    max_open_connections    = null
  }]

  mongodbatlas = [{
    private_key = null
    project_id  = null
    public_key  = null
  }]

  mssql = [{
    connection_url          = null
    max_connection_lifetime = null
    max_idle_connections    = null
    max_open_connections    = null
  }]

  mysql = [{
    connection_url          = null
    max_connection_lifetime = null
    max_idle_connections    = null
    max_open_connections    = null
  }]

  mysql_aurora = [{
    connection_url          = null
    max_connection_lifetime = null
    max_idle_connections    = null
    max_open_connections    = null
  }]

  mysql_legacy = [{
    connection_url          = null
    max_connection_lifetime = null
    max_idle_connections    = null
    max_open_connections    = null
  }]

  mysql_rds = [{
    connection_url          = null
    max_connection_lifetime = null
    max_idle_connections    = null
    max_open_connections    = null
  }]

  oracle = [{
    connection_url          = null
    max_connection_lifetime = null
    max_idle_connections    = null
    max_open_connections    = null
  }]

  postgresql = [{
    connection_url          = null
    max_connection_lifetime = null
    max_idle_connections    = null
    max_open_connections    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allowed_roles" {
  description = "(optional) - A list of roles that are allowed to use this connection."
  type        = list(string)
  default     = null
}

variable "backend" {
  description = "(required) - Unique name of the Vault mount to configure."
  type        = string
}

variable "data" {
  description = "(optional) - A map of sensitive data to pass to the endpoint. Useful for templated connection strings."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the database connection."
  type        = string
}

variable "root_rotation_statements" {
  description = "(optional) - A list of database statements to be executed to rotate the root user's credentials."
  type        = list(string)
  default     = null
}

variable "verify_connection" {
  description = "(optional) - Specifies if the connection is verified during initial configuration."
  type        = bool
  default     = null
}

variable "cassandra" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connect_timeout  = number
      hosts            = list(string)
      insecure_tls     = bool
      password         = string
      pem_bundle       = string
      pem_json         = string
      port             = number
      protocol_version = number
      tls              = bool
      username         = string
    }
  ))
  default = []
}

variable "elasticsearch" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      password = string
      url      = string
      username = string
    }
  ))
  default = []
}

variable "hana" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connection_url          = string
      max_connection_lifetime = number
      max_idle_connections    = number
      max_open_connections    = number
    }
  ))
  default = []
}

variable "mongodb" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connection_url          = string
      max_connection_lifetime = number
      max_idle_connections    = number
      max_open_connections    = number
    }
  ))
  default = []
}

variable "mongodbatlas" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      private_key = string
      project_id  = string
      public_key  = string
    }
  ))
  default = []
}

variable "mssql" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connection_url          = string
      max_connection_lifetime = number
      max_idle_connections    = number
      max_open_connections    = number
    }
  ))
  default = []
}

variable "mysql" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connection_url          = string
      max_connection_lifetime = number
      max_idle_connections    = number
      max_open_connections    = number
    }
  ))
  default = []
}

variable "mysql_aurora" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connection_url          = string
      max_connection_lifetime = number
      max_idle_connections    = number
      max_open_connections    = number
    }
  ))
  default = []
}

variable "mysql_legacy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connection_url          = string
      max_connection_lifetime = number
      max_idle_connections    = number
      max_open_connections    = number
    }
  ))
  default = []
}

variable "mysql_rds" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connection_url          = string
      max_connection_lifetime = number
      max_idle_connections    = number
      max_open_connections    = number
    }
  ))
  default = []
}

variable "oracle" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connection_url          = string
      max_connection_lifetime = number
      max_idle_connections    = number
      max_open_connections    = number
    }
  ))
  default = []
}

variable "postgresql" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connection_url          = string
      max_connection_lifetime = number
      max_idle_connections    = number
      max_open_connections    = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vault_database_secret_backend_connection" "this" {
  allowed_roles            = var.allowed_roles
  backend                  = var.backend
  data                     = var.data
  name                     = var.name
  root_rotation_statements = var.root_rotation_statements
  verify_connection        = var.verify_connection

  dynamic "cassandra" {
    for_each = var.cassandra
    content {
      connect_timeout  = cassandra.value["connect_timeout"]
      hosts            = cassandra.value["hosts"]
      insecure_tls     = cassandra.value["insecure_tls"]
      password         = cassandra.value["password"]
      pem_bundle       = cassandra.value["pem_bundle"]
      pem_json         = cassandra.value["pem_json"]
      port             = cassandra.value["port"]
      protocol_version = cassandra.value["protocol_version"]
      tls              = cassandra.value["tls"]
      username         = cassandra.value["username"]
    }
  }

  dynamic "elasticsearch" {
    for_each = var.elasticsearch
    content {
      password = elasticsearch.value["password"]
      url      = elasticsearch.value["url"]
      username = elasticsearch.value["username"]
    }
  }

  dynamic "hana" {
    for_each = var.hana
    content {
      connection_url          = hana.value["connection_url"]
      max_connection_lifetime = hana.value["max_connection_lifetime"]
      max_idle_connections    = hana.value["max_idle_connections"]
      max_open_connections    = hana.value["max_open_connections"]
    }
  }

  dynamic "mongodb" {
    for_each = var.mongodb
    content {
      connection_url          = mongodb.value["connection_url"]
      max_connection_lifetime = mongodb.value["max_connection_lifetime"]
      max_idle_connections    = mongodb.value["max_idle_connections"]
      max_open_connections    = mongodb.value["max_open_connections"]
    }
  }

  dynamic "mongodbatlas" {
    for_each = var.mongodbatlas
    content {
      private_key = mongodbatlas.value["private_key"]
      project_id  = mongodbatlas.value["project_id"]
      public_key  = mongodbatlas.value["public_key"]
    }
  }

  dynamic "mssql" {
    for_each = var.mssql
    content {
      connection_url          = mssql.value["connection_url"]
      max_connection_lifetime = mssql.value["max_connection_lifetime"]
      max_idle_connections    = mssql.value["max_idle_connections"]
      max_open_connections    = mssql.value["max_open_connections"]
    }
  }

  dynamic "mysql" {
    for_each = var.mysql
    content {
      connection_url          = mysql.value["connection_url"]
      max_connection_lifetime = mysql.value["max_connection_lifetime"]
      max_idle_connections    = mysql.value["max_idle_connections"]
      max_open_connections    = mysql.value["max_open_connections"]
    }
  }

  dynamic "mysql_aurora" {
    for_each = var.mysql_aurora
    content {
      connection_url          = mysql_aurora.value["connection_url"]
      max_connection_lifetime = mysql_aurora.value["max_connection_lifetime"]
      max_idle_connections    = mysql_aurora.value["max_idle_connections"]
      max_open_connections    = mysql_aurora.value["max_open_connections"]
    }
  }

  dynamic "mysql_legacy" {
    for_each = var.mysql_legacy
    content {
      connection_url          = mysql_legacy.value["connection_url"]
      max_connection_lifetime = mysql_legacy.value["max_connection_lifetime"]
      max_idle_connections    = mysql_legacy.value["max_idle_connections"]
      max_open_connections    = mysql_legacy.value["max_open_connections"]
    }
  }

  dynamic "mysql_rds" {
    for_each = var.mysql_rds
    content {
      connection_url          = mysql_rds.value["connection_url"]
      max_connection_lifetime = mysql_rds.value["max_connection_lifetime"]
      max_idle_connections    = mysql_rds.value["max_idle_connections"]
      max_open_connections    = mysql_rds.value["max_open_connections"]
    }
  }

  dynamic "oracle" {
    for_each = var.oracle
    content {
      connection_url          = oracle.value["connection_url"]
      max_connection_lifetime = oracle.value["max_connection_lifetime"]
      max_idle_connections    = oracle.value["max_idle_connections"]
      max_open_connections    = oracle.value["max_open_connections"]
    }
  }

  dynamic "postgresql" {
    for_each = var.postgresql
    content {
      connection_url          = postgresql.value["connection_url"]
      max_connection_lifetime = postgresql.value["max_connection_lifetime"]
      max_idle_connections    = postgresql.value["max_idle_connections"]
      max_open_connections    = postgresql.value["max_open_connections"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_database_secret_backend_connection.this.id
}

output "this" {
  value = vault_database_secret_backend_connection.this
}
```

[top](#index)