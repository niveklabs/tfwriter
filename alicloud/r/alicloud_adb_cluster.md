# alicloud_adb_cluster

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_adb_cluster" {
  source = "./modules/alicloud/r/alicloud_adb_cluster"

  # auto_renew_period - (optional) is a type of number
  auto_renew_period = null
  # db_cluster_category - (required) is a type of string
  db_cluster_category = null
  # db_cluster_version - (optional) is a type of string
  db_cluster_version = null
  # db_node_class - (required) is a type of string
  db_node_class = null
  # db_node_count - (required) is a type of number
  db_node_count = null
  # db_node_storage - (required) is a type of number
  db_node_storage = null
  # description - (optional) is a type of string
  description = null
  # maintain_time - (optional) is a type of string
  maintain_time = null
  # pay_type - (optional) is a type of string
  pay_type = null
  # period - (optional) is a type of number
  period = null
  # renewal_status - (optional) is a type of string
  renewal_status = null
  # security_ips - (optional) is a type of set of string
  security_ips = []
  # tags - (optional) is a type of map of string
  tags = {}
  # vswitch_id - (required) is a type of string
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
variable "auto_renew_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "db_cluster_category" {
  description = "(required)"
  type        = string
}

variable "db_cluster_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_node_class" {
  description = "(required)"
  type        = string
}

variable "db_node_count" {
  description = "(required)"
  type        = number
}

variable "db_node_storage" {
  description = "(required)"
  type        = number
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maintain_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pay_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "renewal_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_ips" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vswitch_id" {
  description = "(required)"
  type        = string
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
resource "alicloud_adb_cluster" "this" {
  auto_renew_period   = var.auto_renew_period
  db_cluster_category = var.db_cluster_category
  db_cluster_version  = var.db_cluster_version
  db_node_class       = var.db_node_class
  db_node_count       = var.db_node_count
  db_node_storage     = var.db_node_storage
  description         = var.description
  maintain_time       = var.maintain_time
  pay_type            = var.pay_type
  period              = var.period
  renewal_status      = var.renewal_status
  security_ips        = var.security_ips
  tags                = var.tags
  vswitch_id          = var.vswitch_id
  zone_id             = var.zone_id

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
output "connection_string" {
  description = "returns a string"
  value       = alicloud_adb_cluster.this.connection_string
}

output "id" {
  description = "returns a string"
  value       = alicloud_adb_cluster.this.id
}

output "maintain_time" {
  description = "returns a string"
  value       = alicloud_adb_cluster.this.maintain_time
}

output "security_ips" {
  description = "returns a set of string"
  value       = alicloud_adb_cluster.this.security_ips
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_adb_cluster.this.zone_id
}

output "this" {
  value = alicloud_adb_cluster.this
}
```

[top](#index)