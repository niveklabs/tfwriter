# alicloud_db_instance

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_db_instance" {
  source = "./modules/alicloud/r/alicloud_db_instance"

  # auto_renew - (optional) is a type of bool
  auto_renew = null
  # auto_renew_period - (optional) is a type of number
  auto_renew_period = null
  # auto_upgrade_minor_version - (optional) is a type of string
  auto_upgrade_minor_version = null
  # db_instance_storage_type - (optional) is a type of string
  db_instance_storage_type = null
  # encryption_key - (optional) is a type of string
  encryption_key = null
  # engine - (required) is a type of string
  engine = null
  # engine_version - (required) is a type of string
  engine_version = null
  # force_restart - (optional) is a type of bool
  force_restart = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # instance_name - (optional) is a type of string
  instance_name = null
  # instance_storage - (required) is a type of number
  instance_storage = null
  # instance_type - (required) is a type of string
  instance_type = null
  # maintain_time - (optional) is a type of string
  maintain_time = null
  # monitoring_period - (optional) is a type of number
  monitoring_period = null
  # period - (optional) is a type of number
  period = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # security_group_ids - (optional) is a type of set of string
  security_group_ids = []
  # security_ip_mode - (optional) is a type of string
  security_ip_mode = null
  # security_ips - (optional) is a type of set of string
  security_ips = []
  # sql_collector_config_value - (optional) is a type of number
  sql_collector_config_value = null
  # sql_collector_status - (optional) is a type of string
  sql_collector_status = null
  # ssl_action - (optional) is a type of string
  ssl_action = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tde_status - (optional) is a type of string
  tde_status = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
  # zone_id - (optional) is a type of string
  zone_id = null
  # zone_id_slave_a - (optional) is a type of string
  zone_id_slave_a = null
  # zone_id_slave_b - (optional) is a type of string
  zone_id_slave_b = null

  parameters = [{
    name  = null
    value = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_renew" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_renew_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto_upgrade_minor_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_instance_storage_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encryption_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine" {
  description = "(required)"
  type        = string
}

variable "engine_version" {
  description = "(required)"
  type        = string
}

variable "force_restart" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_storage" {
  description = "(required)"
  type        = number
}

variable "instance_type" {
  description = "(required)"
  type        = string
}

variable "maintain_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitoring_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "security_ip_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_ips" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "sql_collector_config_value" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sql_collector_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tde_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id_slave_a" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id_slave_b" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameters" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_db_instance" "this" {
  # auto_renew - (optional) is a type of bool
  auto_renew = var.auto_renew
  # auto_renew_period - (optional) is a type of number
  auto_renew_period = var.auto_renew_period
  # auto_upgrade_minor_version - (optional) is a type of string
  auto_upgrade_minor_version = var.auto_upgrade_minor_version
  # db_instance_storage_type - (optional) is a type of string
  db_instance_storage_type = var.db_instance_storage_type
  # encryption_key - (optional) is a type of string
  encryption_key = var.encryption_key
  # engine - (required) is a type of string
  engine = var.engine
  # engine_version - (required) is a type of string
  engine_version = var.engine_version
  # force_restart - (optional) is a type of bool
  force_restart = var.force_restart
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = var.instance_charge_type
  # instance_name - (optional) is a type of string
  instance_name = var.instance_name
  # instance_storage - (required) is a type of number
  instance_storage = var.instance_storage
  # instance_type - (required) is a type of string
  instance_type = var.instance_type
  # maintain_time - (optional) is a type of string
  maintain_time = var.maintain_time
  # monitoring_period - (optional) is a type of number
  monitoring_period = var.monitoring_period
  # period - (optional) is a type of number
  period = var.period
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # security_group_id - (optional) is a type of string
  security_group_id = var.security_group_id
  # security_group_ids - (optional) is a type of set of string
  security_group_ids = var.security_group_ids
  # security_ip_mode - (optional) is a type of string
  security_ip_mode = var.security_ip_mode
  # security_ips - (optional) is a type of set of string
  security_ips = var.security_ips
  # sql_collector_config_value - (optional) is a type of number
  sql_collector_config_value = var.sql_collector_config_value
  # sql_collector_status - (optional) is a type of string
  sql_collector_status = var.sql_collector_status
  # ssl_action - (optional) is a type of string
  ssl_action = var.ssl_action
  # tags - (optional) is a type of map of string
  tags = var.tags
  # tde_status - (optional) is a type of string
  tde_status = var.tde_status
  # vswitch_id - (optional) is a type of string
  vswitch_id = var.vswitch_id
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id
  # zone_id_slave_a - (optional) is a type of string
  zone_id_slave_a = var.zone_id_slave_a
  # zone_id_slave_b - (optional) is a type of string
  zone_id_slave_b = var.zone_id_slave_b

  dynamic "parameters" {
    for_each = var.parameters
    content {
      # name - (required) is a type of string
      name = parameters.value["name"]
      # value - (required) is a type of string
      value = parameters.value["value"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auto_upgrade_minor_version" {
  description = "returns a string"
  value       = alicloud_db_instance.this.auto_upgrade_minor_version
}

output "connection_string" {
  description = "returns a string"
  value       = alicloud_db_instance.this.connection_string
}

output "db_instance_storage_type" {
  description = "returns a string"
  value       = alicloud_db_instance.this.db_instance_storage_type
}

output "id" {
  description = "returns a string"
  value       = alicloud_db_instance.this.id
}

output "maintain_time" {
  description = "returns a string"
  value       = alicloud_db_instance.this.maintain_time
}

output "monitoring_period" {
  description = "returns a number"
  value       = alicloud_db_instance.this.monitoring_period
}

output "port" {
  description = "returns a string"
  value       = alicloud_db_instance.this.port
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_db_instance.this.resource_group_id
}

output "security_group_id" {
  description = "returns a string"
  value       = alicloud_db_instance.this.security_group_id
}

output "security_group_ids" {
  description = "returns a set of string"
  value       = alicloud_db_instance.this.security_group_ids
}

output "security_ips" {
  description = "returns a set of string"
  value       = alicloud_db_instance.this.security_ips
}

output "sql_collector_status" {
  description = "returns a string"
  value       = alicloud_db_instance.this.sql_collector_status
}

output "ssl_action" {
  description = "returns a string"
  value       = alicloud_db_instance.this.ssl_action
}

output "ssl_status" {
  description = "returns a string"
  value       = alicloud_db_instance.this.ssl_status
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_db_instance.this.zone_id
}

output "this" {
  value = alicloud_db_instance.this
}
```

[top](#index)