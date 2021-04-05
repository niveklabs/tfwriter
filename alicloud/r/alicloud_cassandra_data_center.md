# alicloud_cassandra_data_center

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
module "alicloud_cassandra_data_center" {
  source = "./modules/alicloud/r/alicloud_cassandra_data_center"

  # auto_renew - (optional) is a type of bool
  auto_renew = null
  # auto_renew_period - (optional) is a type of number
  auto_renew_period = null
  # cluster_id - (required) is a type of string
  cluster_id = null
  # data_center_name - (optional) is a type of string
  data_center_name = null
  # disk_size - (optional) is a type of number
  disk_size = null
  # disk_type - (optional) is a type of string
  disk_type = null
  # enable_public - (optional) is a type of bool
  enable_public = null
  # instance_type - (required) is a type of string
  instance_type = null
  # node_count - (required) is a type of number
  node_count = null
  # pay_type - (required) is a type of string
  pay_type = null
  # period - (optional) is a type of number
  period = null
  # period_unit - (optional) is a type of string
  period_unit = null
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

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "data_center_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disk_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_public" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_type" {
  description = "(required)"
  type        = string
}

variable "node_count" {
  description = "(required)"
  type        = number
}

variable "pay_type" {
  description = "(required)"
  type        = string
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "period_unit" {
  description = "(optional)"
  type        = string
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
resource "alicloud_cassandra_data_center" "this" {
  auto_renew        = var.auto_renew
  auto_renew_period = var.auto_renew_period
  cluster_id        = var.cluster_id
  data_center_name  = var.data_center_name
  disk_size         = var.disk_size
  disk_type         = var.disk_type
  enable_public     = var.enable_public
  instance_type     = var.instance_type
  node_count        = var.node_count
  pay_type          = var.pay_type
  period            = var.period
  period_unit       = var.period_unit
  vswitch_id        = var.vswitch_id
  zone_id           = var.zone_id

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
output "data_center_id" {
  description = "returns a string"
  value       = alicloud_cassandra_data_center.this.data_center_id
}

output "id" {
  description = "returns a string"
  value       = alicloud_cassandra_data_center.this.id
}

output "public_points" {
  description = "returns a list of string"
  value       = alicloud_cassandra_data_center.this.public_points
}

output "status" {
  description = "returns a string"
  value       = alicloud_cassandra_data_center.this.status
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_cassandra_data_center.this.zone_id
}

output "this" {
  value = alicloud_cassandra_data_center.this
}
```

[top](#index)