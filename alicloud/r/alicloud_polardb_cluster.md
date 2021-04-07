# alicloud_polardb_cluster

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
module "alicloud_polardb_cluster" {
  source = "./modules/alicloud/r/alicloud_polardb_cluster"

  # auto_renew_period - (optional) is a type of number
  auto_renew_period = null
  # collector_status - (optional) is a type of string
  collector_status = null
  # db_node_class - (required) is a type of string
  db_node_class = null
  # db_node_count - (optional) is a type of number
  db_node_count = null
  # db_type - (required) is a type of string
  db_type = null
  # db_version - (required) is a type of string
  db_version = null
  # description - (optional) is a type of string
  description = null
  # maintain_time - (optional) is a type of string
  maintain_time = null
  # modify_type - (optional) is a type of string
  modify_type = null
  # pay_type - (optional) is a type of string
  pay_type = null
  # period - (optional) is a type of number
  period = null
  # renewal_status - (optional) is a type of string
  renewal_status = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # security_ips - (optional) is a type of set of string
  security_ips = []
  # tags - (optional) is a type of map of string
  tags = {}
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
  # zone_id - (optional) is a type of string
  zone_id = null

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
variable "auto_renew_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "collector_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_node_class" {
  description = "(required)"
  type        = string
}

variable "db_node_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "db_type" {
  description = "(required)"
  type        = string
}

variable "db_version" {
  description = "(required)"
  type        = string
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

variable "modify_type" {
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

variable "resource_group_id" {
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
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
resource "alicloud_polardb_cluster" "this" {
  # auto_renew_period - (optional) is a type of number
  auto_renew_period = var.auto_renew_period
  # collector_status - (optional) is a type of string
  collector_status = var.collector_status
  # db_node_class - (required) is a type of string
  db_node_class = var.db_node_class
  # db_node_count - (optional) is a type of number
  db_node_count = var.db_node_count
  # db_type - (required) is a type of string
  db_type = var.db_type
  # db_version - (required) is a type of string
  db_version = var.db_version
  # description - (optional) is a type of string
  description = var.description
  # maintain_time - (optional) is a type of string
  maintain_time = var.maintain_time
  # modify_type - (optional) is a type of string
  modify_type = var.modify_type
  # pay_type - (optional) is a type of string
  pay_type = var.pay_type
  # period - (optional) is a type of number
  period = var.period
  # renewal_status - (optional) is a type of string
  renewal_status = var.renewal_status
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # security_ips - (optional) is a type of set of string
  security_ips = var.security_ips
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vswitch_id - (optional) is a type of string
  vswitch_id = var.vswitch_id
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id

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
output "collector_status" {
  description = "returns a string"
  value       = alicloud_polardb_cluster.this.collector_status
}

output "connection_string" {
  description = "returns a string"
  value       = alicloud_polardb_cluster.this.connection_string
}

output "id" {
  description = "returns a string"
  value       = alicloud_polardb_cluster.this.id
}

output "maintain_time" {
  description = "returns a string"
  value       = alicloud_polardb_cluster.this.maintain_time
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_polardb_cluster.this.resource_group_id
}

output "security_ips" {
  description = "returns a set of string"
  value       = alicloud_polardb_cluster.this.security_ips
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_polardb_cluster.this.zone_id
}

output "this" {
  value = alicloud_polardb_cluster.this
}
```

[top](#index)