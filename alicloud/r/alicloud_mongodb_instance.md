# alicloud_mongodb_instance

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
module "alicloud_mongodb_instance" {
  source = "./modules/alicloud/r/alicloud_mongodb_instance"

  # account_password - (optional) is a type of string
  account_password = null
  # backup_period - (optional) is a type of set of string
  backup_period = []
  # backup_time - (optional) is a type of string
  backup_time = null
  # db_instance_class - (required) is a type of string
  db_instance_class = null
  # db_instance_storage - (required) is a type of number
  db_instance_storage = null
  # engine_version - (required) is a type of string
  engine_version = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = null
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = {}
  # maintain_end_time - (optional) is a type of string
  maintain_end_time = null
  # maintain_start_time - (optional) is a type of string
  maintain_start_time = null
  # name - (optional) is a type of string
  name = null
  # period - (optional) is a type of number
  period = null
  # replication_factor - (optional) is a type of number
  replication_factor = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # security_ip_list - (optional) is a type of set of string
  security_ip_list = []
  # ssl_action - (optional) is a type of string
  ssl_action = null
  # storage_engine - (optional) is a type of string
  storage_engine = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tde_status - (optional) is a type of string
  tde_status = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
  # zone_id - (optional) is a type of string
  zone_id = null

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
variable "account_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_period" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "backup_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_instance_class" {
  description = "(required)"
  type        = string
}

variable "db_instance_storage" {
  description = "(required)"
  type        = number
}

variable "engine_version" {
  description = "(required)"
  type        = string
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_encrypted_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_encryption_context" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "maintain_end_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maintain_start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "replication_factor" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_ip_list" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "ssl_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_engine" {
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
resource "alicloud_mongodb_instance" "this" {
  account_password       = var.account_password
  backup_period          = var.backup_period
  backup_time            = var.backup_time
  db_instance_class      = var.db_instance_class
  db_instance_storage    = var.db_instance_storage
  engine_version         = var.engine_version
  instance_charge_type   = var.instance_charge_type
  kms_encrypted_password = var.kms_encrypted_password
  kms_encryption_context = var.kms_encryption_context
  maintain_end_time      = var.maintain_end_time
  maintain_start_time    = var.maintain_start_time
  name                   = var.name
  period                 = var.period
  replication_factor     = var.replication_factor
  security_group_id      = var.security_group_id
  security_ip_list       = var.security_ip_list
  ssl_action             = var.ssl_action
  storage_engine         = var.storage_engine
  tags                   = var.tags
  tde_status             = var.tde_status
  vswitch_id             = var.vswitch_id
  zone_id                = var.zone_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "backup_period" {
  description = "returns a set of string"
  value       = alicloud_mongodb_instance.this.backup_period
}

output "backup_time" {
  description = "returns a string"
  value       = alicloud_mongodb_instance.this.backup_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_mongodb_instance.this.id
}

output "maintain_end_time" {
  description = "returns a string"
  value       = alicloud_mongodb_instance.this.maintain_end_time
}

output "maintain_start_time" {
  description = "returns a string"
  value       = alicloud_mongodb_instance.this.maintain_start_time
}

output "period" {
  description = "returns a number"
  value       = alicloud_mongodb_instance.this.period
}

output "replica_set_name" {
  description = "returns a string"
  value       = alicloud_mongodb_instance.this.replica_set_name
}

output "replication_factor" {
  description = "returns a number"
  value       = alicloud_mongodb_instance.this.replication_factor
}

output "retention_period" {
  description = "returns a number"
  value       = alicloud_mongodb_instance.this.retention_period
}

output "security_group_id" {
  description = "returns a string"
  value       = alicloud_mongodb_instance.this.security_group_id
}

output "security_ip_list" {
  description = "returns a set of string"
  value       = alicloud_mongodb_instance.this.security_ip_list
}

output "ssl_action" {
  description = "returns a string"
  value       = alicloud_mongodb_instance.this.ssl_action
}

output "ssl_status" {
  description = "returns a string"
  value       = alicloud_mongodb_instance.this.ssl_status
}

output "storage_engine" {
  description = "returns a string"
  value       = alicloud_mongodb_instance.this.storage_engine
}

output "vswitch_id" {
  description = "returns a string"
  value       = alicloud_mongodb_instance.this.vswitch_id
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_mongodb_instance.this.zone_id
}

output "this" {
  value = alicloud_mongodb_instance.this
}
```

[top](#index)