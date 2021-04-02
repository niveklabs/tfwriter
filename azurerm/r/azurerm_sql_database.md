# azurerm_sql_database

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
module "azurerm_sql_database" {
  source = "./modules/azurerm/r/azurerm_sql_database"

  # collation - (optional) is a type of string
  collation = null
  # create_mode - (optional) is a type of string
  create_mode = null
  # edition - (optional) is a type of string
  edition = null
  # elastic_pool_name - (optional) is a type of string
  elastic_pool_name = null
  # extended_auditing_policy - (optional) is a type of list of object
  extended_auditing_policy = [{
    log_monitoring_enabled                  = null
    retention_in_days                       = null
    storage_account_access_key              = null
    storage_account_access_key_is_secondary = null
    storage_endpoint                        = null
  }]
  # location - (required) is a type of string
  location = null
  # max_size_bytes - (optional) is a type of string
  max_size_bytes = null
  # max_size_gb - (optional) is a type of string
  max_size_gb = null
  # name - (required) is a type of string
  name = null
  # read_scale - (optional) is a type of bool
  read_scale = null
  # requested_service_objective_id - (optional) is a type of string
  requested_service_objective_id = null
  # requested_service_objective_name - (optional) is a type of string
  requested_service_objective_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # restore_point_in_time - (optional) is a type of string
  restore_point_in_time = null
  # server_name - (required) is a type of string
  server_name = null
  # source_database_deletion_date - (optional) is a type of string
  source_database_deletion_date = null
  # source_database_id - (optional) is a type of string
  source_database_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zone_redundant - (optional) is a type of bool
  zone_redundant = null

  import = [{
    administrator_login          = null
    administrator_login_password = null
    authentication_type          = null
    operation_mode               = null
    storage_key                  = null
    storage_key_type             = null
    storage_uri                  = null
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

variable "edition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "elastic_pool_name" {
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

variable "location" {
  description = "(required)"
  type        = string
}

variable "max_size_bytes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_size_gb" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "read_scale" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "requested_service_objective_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "requested_service_objective_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "restore_point_in_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_name" {
  description = "(required)"
  type        = string
}

variable "source_database_deletion_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_database_id" {
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

variable "import" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      administrator_login          = string
      administrator_login_password = string
      authentication_type          = string
      operation_mode               = string
      storage_key                  = string
      storage_key_type             = string
      storage_uri                  = string
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
resource "azurerm_sql_database" "this" {
  collation                        = var.collation
  create_mode                      = var.create_mode
  edition                          = var.edition
  elastic_pool_name                = var.elastic_pool_name
  extended_auditing_policy         = var.extended_auditing_policy
  location                         = var.location
  max_size_bytes                   = var.max_size_bytes
  max_size_gb                      = var.max_size_gb
  name                             = var.name
  read_scale                       = var.read_scale
  requested_service_objective_id   = var.requested_service_objective_id
  requested_service_objective_name = var.requested_service_objective_name
  resource_group_name              = var.resource_group_name
  restore_point_in_time            = var.restore_point_in_time
  server_name                      = var.server_name
  source_database_deletion_date    = var.source_database_deletion_date
  source_database_id               = var.source_database_id
  tags                             = var.tags
  zone_redundant                   = var.zone_redundant

  dynamic "import" {
    for_each = var.import
    content {
      administrator_login          = import.value["administrator_login"]
      administrator_login_password = import.value["administrator_login_password"]
      authentication_type          = import.value["authentication_type"]
      operation_mode               = import.value["operation_mode"]
      storage_key                  = import.value["storage_key"]
      storage_key_type             = import.value["storage_key_type"]
      storage_uri                  = import.value["storage_uri"]
    }
  }

  dynamic "threat_detection_policy" {
    for_each = var.threat_detection_policy
    content {
      disabled_alerts            = threat_detection_policy.value["disabled_alerts"]
      email_account_admins       = threat_detection_policy.value["email_account_admins"]
      email_addresses            = threat_detection_policy.value["email_addresses"]
      retention_days             = threat_detection_policy.value["retention_days"]
      state                      = threat_detection_policy.value["state"]
      storage_account_access_key = threat_detection_policy.value["storage_account_access_key"]
      storage_endpoint           = threat_detection_policy.value["storage_endpoint"]
      use_server_default         = threat_detection_policy.value["use_server_default"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "collation" {
  description = "returns a string"
  value       = azurerm_sql_database.this.collation
}

output "creation_date" {
  description = "returns a string"
  value       = azurerm_sql_database.this.creation_date
}

output "default_secondary_location" {
  description = "returns a string"
  value       = azurerm_sql_database.this.default_secondary_location
}

output "edition" {
  description = "returns a string"
  value       = azurerm_sql_database.this.edition
}

output "elastic_pool_name" {
  description = "returns a string"
  value       = azurerm_sql_database.this.elastic_pool_name
}

output "encryption" {
  description = "returns a string"
  value       = azurerm_sql_database.this.encryption
}

output "extended_auditing_policy" {
  description = "returns a list of object"
  value       = azurerm_sql_database.this.extended_auditing_policy
}

output "id" {
  description = "returns a string"
  value       = azurerm_sql_database.this.id
}

output "max_size_bytes" {
  description = "returns a string"
  value       = azurerm_sql_database.this.max_size_bytes
}

output "max_size_gb" {
  description = "returns a string"
  value       = azurerm_sql_database.this.max_size_gb
}

output "requested_service_objective_id" {
  description = "returns a string"
  value       = azurerm_sql_database.this.requested_service_objective_id
}

output "requested_service_objective_name" {
  description = "returns a string"
  value       = azurerm_sql_database.this.requested_service_objective_name
}

output "restore_point_in_time" {
  description = "returns a string"
  value       = azurerm_sql_database.this.restore_point_in_time
}

output "source_database_deletion_date" {
  description = "returns a string"
  value       = azurerm_sql_database.this.source_database_deletion_date
}

output "source_database_id" {
  description = "returns a string"
  value       = azurerm_sql_database.this.source_database_id
}

output "this" {
  value = azurerm_sql_database.this
}
```

[top](#index)