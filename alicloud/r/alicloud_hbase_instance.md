# alicloud_hbase_instance

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
module "alicloud_hbase_instance" {
  source = "./modules/alicloud/r/alicloud_hbase_instance"

  # account - (optional) is a type of string
  account = null
  # auto_renew - (optional) is a type of bool
  auto_renew = null
  # cold_storage_size - (optional) is a type of number
  cold_storage_size = null
  # core_disk_size - (optional) is a type of number
  core_disk_size = null
  # core_disk_type - (optional) is a type of string
  core_disk_type = null
  # core_instance_quantity - (optional) is a type of number
  core_instance_quantity = null
  # core_instance_type - (required) is a type of string
  core_instance_type = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # duration - (optional) is a type of number
  duration = null
  # engine - (optional) is a type of string
  engine = null
  # engine_version - (required) is a type of string
  engine_version = null
  # immediate_delete_flag - (optional) is a type of bool
  immediate_delete_flag = null
  # ip_white - (optional) is a type of string
  ip_white = null
  # maintain_end_time - (optional) is a type of string
  maintain_end_time = null
  # maintain_start_time - (optional) is a type of string
  maintain_start_time = null
  # master_instance_type - (required) is a type of string
  master_instance_type = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # pay_type - (optional) is a type of string
  pay_type = null
  # security_groups - (optional) is a type of list of string
  security_groups = []
  # tags - (optional) is a type of map of string
  tags = {}
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
variable "account" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_renew" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cold_storage_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "core_disk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "core_disk_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "core_instance_quantity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "core_instance_type" {
  description = "(required)"
  type        = string
}

variable "deletion_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "engine" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_version" {
  description = "(required)"
  type        = string
}

variable "immediate_delete_flag" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip_white" {
  description = "(optional)"
  type        = string
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

variable "master_instance_type" {
  description = "(required)"
  type        = string
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

variable "pay_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_groups" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
resource "alicloud_hbase_instance" "this" {
  account                = var.account
  auto_renew             = var.auto_renew
  cold_storage_size      = var.cold_storage_size
  core_disk_size         = var.core_disk_size
  core_disk_type         = var.core_disk_type
  core_instance_quantity = var.core_instance_quantity
  core_instance_type     = var.core_instance_type
  deletion_protection    = var.deletion_protection
  duration               = var.duration
  engine                 = var.engine
  engine_version         = var.engine_version
  immediate_delete_flag  = var.immediate_delete_flag
  ip_white               = var.ip_white
  maintain_end_time      = var.maintain_end_time
  maintain_start_time    = var.maintain_start_time
  master_instance_type   = var.master_instance_type
  name                   = var.name
  password               = var.password
  pay_type               = var.pay_type
  security_groups        = var.security_groups
  tags                   = var.tags
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
output "auto_renew" {
  description = "returns a bool"
  value       = alicloud_hbase_instance.this.auto_renew
}

output "duration" {
  description = "returns a number"
  value       = alicloud_hbase_instance.this.duration
}

output "id" {
  description = "returns a string"
  value       = alicloud_hbase_instance.this.id
}

output "ip_white" {
  description = "returns a string"
  value       = alicloud_hbase_instance.this.ip_white
}

output "maintain_end_time" {
  description = "returns a string"
  value       = alicloud_hbase_instance.this.maintain_end_time
}

output "maintain_start_time" {
  description = "returns a string"
  value       = alicloud_hbase_instance.this.maintain_start_time
}

output "master_instance_quantity" {
  description = "returns a number"
  value       = alicloud_hbase_instance.this.master_instance_quantity
}

output "security_groups" {
  description = "returns a list of string"
  value       = alicloud_hbase_instance.this.security_groups
}

output "slb_conn_addrs" {
  description = "returns a list of object"
  value       = alicloud_hbase_instance.this.slb_conn_addrs
}

output "ui_proxy_conn_addrs" {
  description = "returns a list of object"
  value       = alicloud_hbase_instance.this.ui_proxy_conn_addrs
}

output "zk_conn_addrs" {
  description = "returns a list of object"
  value       = alicloud_hbase_instance.this.zk_conn_addrs
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_hbase_instance.this.zone_id
}

output "this" {
  value = alicloud_hbase_instance.this
}
```

[top](#index)