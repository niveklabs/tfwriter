# grafana_data_source

[back](../grafana.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    grafana = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "grafana_data_source" {
  source = "./modules/grafana/r/grafana_data_source"

  # access_mode - (optional) is a type of string
  access_mode = null
  # basic_auth_enabled - (optional) is a type of bool
  basic_auth_enabled = null
  # basic_auth_password - (optional) is a type of string
  basic_auth_password = null
  # basic_auth_username - (optional) is a type of string
  basic_auth_username = null
  # database_name - (optional) is a type of string
  database_name = null
  # is_default - (optional) is a type of bool
  is_default = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # type - (required) is a type of string
  type = null
  # url - (optional) is a type of string
  url = null
  # username - (optional) is a type of string
  username = null

  json_data = [{
    assume_role_arn           = null
    auth_type                 = null
    conn_max_lifetime         = null
    custom_metrics_namespaces = null
    default_region            = null
    encrypt                   = null
    es_version                = null
    graphite_version          = null
    http_method               = null
    interval                  = null
    log_level_field           = null
    log_message_field         = null
    max_idle_conns            = null
    max_open_conns            = null
    postgres_version          = null
    query_timeout             = null
    ssl_mode                  = null
    time_field                = null
    time_interval             = null
    timescaledb               = null
    tls_auth                  = null
    tls_auth_with_ca_cert     = null
    tls_skip_verify           = null
    tsdb_resolution           = null
    tsdb_version              = null
  }]

  secure_json_data = [{
    access_key          = null
    basic_auth_password = null
    password            = null
    private_key         = null
    secret_key          = null
    tls_ca_cert         = null
    tls_client_cert     = null
    tls_client_key      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "basic_auth_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "basic_auth_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "basic_auth_username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_default" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "json_data" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      assume_role_arn           = string
      auth_type                 = string
      conn_max_lifetime         = number
      custom_metrics_namespaces = string
      default_region            = string
      encrypt                   = string
      es_version                = number
      graphite_version          = string
      http_method               = string
      interval                  = string
      log_level_field           = string
      log_message_field         = string
      max_idle_conns            = number
      max_open_conns            = number
      postgres_version          = number
      query_timeout             = string
      ssl_mode                  = string
      time_field                = string
      time_interval             = string
      timescaledb               = bool
      tls_auth                  = bool
      tls_auth_with_ca_cert     = bool
      tls_skip_verify           = bool
      tsdb_resolution           = string
      tsdb_version              = string
    }
  ))
  default = []
}

variable "secure_json_data" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_key          = string
      basic_auth_password = string
      password            = string
      private_key         = string
      secret_key          = string
      tls_ca_cert         = string
      tls_client_cert     = string
      tls_client_key      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "grafana_data_source" "this" {
  access_mode         = var.access_mode
  basic_auth_enabled  = var.basic_auth_enabled
  basic_auth_password = var.basic_auth_password
  basic_auth_username = var.basic_auth_username
  database_name       = var.database_name
  is_default          = var.is_default
  name                = var.name
  password            = var.password
  type                = var.type
  url                 = var.url
  username            = var.username

  dynamic "json_data" {
    for_each = var.json_data
    content {
      assume_role_arn           = json_data.value["assume_role_arn"]
      auth_type                 = json_data.value["auth_type"]
      conn_max_lifetime         = json_data.value["conn_max_lifetime"]
      custom_metrics_namespaces = json_data.value["custom_metrics_namespaces"]
      default_region            = json_data.value["default_region"]
      encrypt                   = json_data.value["encrypt"]
      es_version                = json_data.value["es_version"]
      graphite_version          = json_data.value["graphite_version"]
      http_method               = json_data.value["http_method"]
      interval                  = json_data.value["interval"]
      log_level_field           = json_data.value["log_level_field"]
      log_message_field         = json_data.value["log_message_field"]
      max_idle_conns            = json_data.value["max_idle_conns"]
      max_open_conns            = json_data.value["max_open_conns"]
      postgres_version          = json_data.value["postgres_version"]
      query_timeout             = json_data.value["query_timeout"]
      ssl_mode                  = json_data.value["ssl_mode"]
      time_field                = json_data.value["time_field"]
      time_interval             = json_data.value["time_interval"]
      timescaledb               = json_data.value["timescaledb"]
      tls_auth                  = json_data.value["tls_auth"]
      tls_auth_with_ca_cert     = json_data.value["tls_auth_with_ca_cert"]
      tls_skip_verify           = json_data.value["tls_skip_verify"]
      tsdb_resolution           = json_data.value["tsdb_resolution"]
      tsdb_version              = json_data.value["tsdb_version"]
    }
  }

  dynamic "secure_json_data" {
    for_each = var.secure_json_data
    content {
      access_key          = secure_json_data.value["access_key"]
      basic_auth_password = secure_json_data.value["basic_auth_password"]
      password            = secure_json_data.value["password"]
      private_key         = secure_json_data.value["private_key"]
      secret_key          = secure_json_data.value["secret_key"]
      tls_ca_cert         = secure_json_data.value["tls_ca_cert"]
      tls_client_cert     = secure_json_data.value["tls_client_cert"]
      tls_client_key      = secure_json_data.value["tls_client_key"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = grafana_data_source.this.id
}

output "this" {
  value = grafana_data_source.this
}
```

[top](#index)