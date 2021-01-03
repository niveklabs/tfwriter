# alicloud_mongodb_sharding_instance

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_mongodb_sharding_instance" {
  source = "./modules/alicloud/r/alicloud_mongodb_sharding_instance"

  # account_password - (optional) is a type of string
  account_password = null
  # backup_period - (optional) is a type of set of string
  backup_period = []
  # backup_time - (optional) is a type of string
  backup_time = null
  # engine_version - (required) is a type of string
  engine_version = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = null
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = {}
  # name - (optional) is a type of string
  name = null
  # period - (optional) is a type of number
  period = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # security_ip_list - (optional) is a type of set of string
  security_ip_list = []
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

  mongo_list = [{
    connect_string = null
    node_class     = null
    node_id        = null
    port           = null
  }]

  shard_list = [{
    node_class   = null
    node_id      = null
    node_storage = null
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

variable "mongo_list" {
  description = "nested block: NestingList, min items: 2, max items: 32"
  type = set(object(
    {
      connect_string = string
      node_class     = string
      node_id        = string
      port           = number
    }
  ))
}

variable "shard_list" {
  description = "nested block: NestingList, min items: 2, max items: 32"
  type = set(object(
    {
      node_class   = string
      node_id      = string
      node_storage = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_mongodb_sharding_instance" "this" {
  account_password       = var.account_password
  backup_period          = var.backup_period
  backup_time            = var.backup_time
  engine_version         = var.engine_version
  instance_charge_type   = var.instance_charge_type
  kms_encrypted_password = var.kms_encrypted_password
  kms_encryption_context = var.kms_encryption_context
  name                   = var.name
  period                 = var.period
  security_group_id      = var.security_group_id
  security_ip_list       = var.security_ip_list
  storage_engine         = var.storage_engine
  tags                   = var.tags
  tde_status             = var.tde_status
  vswitch_id             = var.vswitch_id
  zone_id                = var.zone_id

  dynamic "mongo_list" {
    for_each = var.mongo_list
    content {
      node_class = mongo_list.value["node_class"]
    }
  }

  dynamic "shard_list" {
    for_each = var.shard_list
    content {
      node_class   = shard_list.value["node_class"]
      node_storage = shard_list.value["node_storage"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "backup_period" {
  description = "returns a set of string"
  value       = alicloud_mongodb_sharding_instance.this.backup_period
}

output "backup_time" {
  description = "returns a string"
  value       = alicloud_mongodb_sharding_instance.this.backup_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_mongodb_sharding_instance.this.id
}

output "instance_charge_type" {
  description = "returns a string"
  value       = alicloud_mongodb_sharding_instance.this.instance_charge_type
}

output "period" {
  description = "returns a number"
  value       = alicloud_mongodb_sharding_instance.this.period
}

output "retention_period" {
  description = "returns a number"
  value       = alicloud_mongodb_sharding_instance.this.retention_period
}

output "security_group_id" {
  description = "returns a string"
  value       = alicloud_mongodb_sharding_instance.this.security_group_id
}

output "security_ip_list" {
  description = "returns a set of string"
  value       = alicloud_mongodb_sharding_instance.this.security_ip_list
}

output "storage_engine" {
  description = "returns a string"
  value       = alicloud_mongodb_sharding_instance.this.storage_engine
}

output "this" {
  value = alicloud_mongodb_sharding_instance.this
}
```

[top](#index)