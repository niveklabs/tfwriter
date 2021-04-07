# azurerm_mssql_database

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_mssql_database" {
  source = "./modules/azurerm/r/azurerm_mssql_database"

  # auto_pause_delay_in_minutes - (optional) is a type of number
  auto_pause_delay_in_minutes = null
  # collation - (optional) is a type of string
  collation = null
  # create_mode - (optional) is a type of string
  create_mode = null
  # creation_source_database_id - (optional) is a type of string
  creation_source_database_id = null
  # elastic_pool_id - (optional) is a type of string
  elastic_pool_id = null
  # extended_auditing_policy - (optional) is a type of list of object
  extended_auditing_policy = [{
    log_monitoring_enabled                  = null
    retention_in_days                       = null
    storage_account_access_key              = null
    storage_account_access_key_is_secondary = null
    storage_endpoint                        = null
  }]
  # license_type - (optional) is a type of string
  license_type = null
  # max_size_gb - (optional) is a type of number
  max_size_gb = null
  # min_capacity - (optional) is a type of number
  min_capacity = null
  # name - (required) is a type of string
  name = null
  # read_replica_count - (optional) is a type of number
  read_replica_count = null
  # read_scale - (optional) is a type of bool
  read_scale = null
  # recover_database_id - (optional) is a type of string
  recover_database_id = null
  # restore_dropped_database_id - (optional) is a type of string
  restore_dropped_database_id = null
  # restore_point_in_time - (optional) is a type of string
  restore_point_in_time = null
  # sample_name - (optional) is a type of string
  sample_name = null
  # server_id - (required) is a type of string
  server_id = null
  # sku_name - (optional) is a type of string
  sku_name = null
  # storage_account_type - (optional) is a type of string
  storage_account_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zone_redundant - (optional) is a type of bool
  zone_redundant = null

  long_term_retention_policy = [{
    monthly_retention = null
    week_of_year      = null
    weekly_retention  = null
    yearly_retention  = null
  }]

  short_term_retention_policy = [{
    retention_days = null
  }]

  threat_detection_policy = [{
    disabled_alerts            = []
    email_account_admins       = null
    email_addresses            = []
    retention_days             = null
    state                      = null
    storage_account_access_key = null
    storage_endpoint           = null
    use_server_default         = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_pause_delay_in_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "collation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "create_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "creation_source_database_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "elastic_pool_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extended_auditing_policy" {
  description = "(optional)"
  type = list(object(
    {
      log_monitoring_enabled                  = bool
      retention_in_days                       = number
      storage_account_access_key              = string
      storage_account_access_key_is_secondary = bool
      storage_endpoint                        = string
    }
  ))
  default = null
}

variable "license_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_size_gb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "read_replica_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "read_scale" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "recover_database_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "restore_dropped_database_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "restore_point_in_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sample_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_id" {
  description = "(required)"
  type        = string
}

variable "sku_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_account_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "zone_redundant" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "long_term_retention_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      monthly_retention = string
      week_of_year      = number
      weekly_retention  = string
      yearly_retention  = string
    }
  ))
  default = []
}

variable "short_term_retention_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      retention_days = number
    }
  ))
  default = []
}

variable "threat_detection_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disabled_alerts            = set(string)
      email_account_admins       = string
      email_addresses            = set(string)
      retention_days             = number
      state                      = string
      storage_account_access_key = string
      storage_endpoint           = string
      use_server_default         = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_mssql_database" "this" {
  # auto_pause_delay_in_minutes - (optional) is a type of number
  auto_pause_delay_in_minutes = var.auto_pause_delay_in_minutes
  # collation - (optional) is a type of string
  collation = var.collation
  # create_mode - (optional) is a type of string
  create_mode = var.create_mode
  # creation_source_database_id - (optional) is a type of string
  creation_source_database_id = var.creation_source_database_id
  # elastic_pool_id - (optional) is a type of string
  elastic_pool_id = var.elastic_pool_id
  # extended_auditing_policy - (optional) is a type of list of object
  extended_auditing_policy = var.extended_auditing_policy
  # license_type - (optional) is a type of string
  license_type = var.license_type
  # max_size_gb - (optional) is a type of number
  max_size_gb = var.max_size_gb
  # min_capacity - (optional) is a type of number
  min_capacity = var.min_capacity
  # name - (required) is a type of string
  name = var.name
  # read_replica_count - (optional) is a type of number
  read_replica_count = var.read_replica_count
  # read_scale - (optional) is a type of bool
  read_scale = var.read_scale
  # recover_database_id - (optional) is a type of string
  recover_database_id = var.recover_database_id
  # restore_dropped_database_id - (optional) is a type of string
  restore_dropped_database_id = var.restore_dropped_database_id
  # restore_point_in_time - (optional) is a type of string
  restore_point_in_time = var.restore_point_in_time
  # sample_name - (optional) is a type of string
  sample_name = var.sample_name
  # server_id - (required) is a type of string
  server_id = var.server_id
  # sku_name - (optional) is a type of string
  sku_name = var.sku_name
  # storage_account_type - (optional) is a type of string
  storage_account_type = var.storage_account_type
  # tags - (optional) is a type of map of string
  tags = var.tags
  # zone_redundant - (optional) is a type of bool
  zone_redundant = var.zone_redundant

  dynamic "long_term_retention_policy" {
    for_each = var.long_term_retention_policy
    content {
      # monthly_retention - (optional) is a type of string
      monthly_retention = long_term_retention_policy.value["monthly_retention"]
      # week_of_year - (optional) is a type of number
      week_of_year = long_term_retention_policy.value["week_of_year"]
      # weekly_retention - (optional) is a type of string
      weekly_retention = long_term_retention_policy.value["weekly_retention"]
      # yearly_retention - (optional) is a type of string
      yearly_retention = long_term_retention_policy.value["yearly_retention"]
    }
  }

  dynamic "short_term_retention_policy" {
    for_each = var.short_term_retention_policy
    content {
      # retention_days - (required) is a type of number
      retention_days = short_term_retention_policy.value["retention_days"]
    }
  }

  dynamic "threat_detection_policy" {
    for_each = var.threat_detection_policy
    content {
      # disabled_alerts - (optional) is a type of set of string
      disabled_alerts = threat_detection_policy.value["disabled_alerts"]
      # email_account_admins - (optional) is a type of string
      email_account_admins = threat_detection_policy.value["email_account_admins"]
      # email_addresses - (optional) is a type of set of string
      email_addresses = threat_detection_policy.value["email_addresses"]
      # retention_days - (optional) is a type of number
      retention_days = threat_detection_policy.value["retention_days"]
      # state - (optional) is a type of string
      state = threat_detection_policy.value["state"]
      # storage_account_access_key - (optional) is a type of string
      storage_account_access_key = threat_detection_policy.value["storage_account_access_key"]
      # storage_endpoint - (optional) is a type of string
      storage_endpoint = threat_detection_policy.value["storage_endpoint"]
      # use_server_default - (optional) is a type of string
      use_server_default = threat_detection_policy.value["use_server_default"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auto_pause_delay_in_minutes" {
  description = "returns a number"
  value       = azurerm_mssql_database.this.auto_pause_delay_in_minutes
}

output "collation" {
  description = "returns a string"
  value       = azurerm_mssql_database.this.collation
}

output "create_mode" {
  description = "returns a string"
  value       = azurerm_mssql_database.this.create_mode
}

output "creation_source_database_id" {
  description = "returns a string"
  value       = azurerm_mssql_database.this.creation_source_database_id
}

output "extended_auditing_policy" {
  description = "returns a list of object"
  value       = azurerm_mssql_database.this.extended_auditing_policy
}

output "id" {
  description = "returns a string"
  value       = azurerm_mssql_database.this.id
}

output "license_type" {
  description = "returns a string"
  value       = azurerm_mssql_database.this.license_type
}

output "max_size_gb" {
  description = "returns a number"
  value       = azurerm_mssql_database.this.max_size_gb
}

output "min_capacity" {
  description = "returns a number"
  value       = azurerm_mssql_database.this.min_capacity
}

output "read_replica_count" {
  description = "returns a number"
  value       = azurerm_mssql_database.this.read_replica_count
}

output "read_scale" {
  description = "returns a bool"
  value       = azurerm_mssql_database.this.read_scale
}

output "restore_point_in_time" {
  description = "returns a string"
  value       = azurerm_mssql_database.this.restore_point_in_time
}

output "sample_name" {
  description = "returns a string"
  value       = azurerm_mssql_database.this.sample_name
}

output "sku_name" {
  description = "returns a string"
  value       = azurerm_mssql_database.this.sku_name
}

output "zone_redundant" {
  description = "returns a bool"
  value       = azurerm_mssql_database.this.zone_redundant
}

output "this" {
  value = azurerm_mssql_database.this
}
```

[top](#index)