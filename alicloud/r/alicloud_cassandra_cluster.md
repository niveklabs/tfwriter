# alicloud_cassandra_cluster

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
module "alicloud_cassandra_cluster" {
  source = "./modules/alicloud/r/alicloud_cassandra_cluster"

  # auto_renew - (optional) is a type of bool
  auto_renew = null
  # auto_renew_period - (optional) is a type of number
  auto_renew_period = null
  # cluster_name - (optional) is a type of string
  cluster_name = null
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
  # ip_white - (optional) is a type of string
  ip_white = null
  # maintain_end_time - (optional) is a type of string
  maintain_end_time = null
  # maintain_start_time - (optional) is a type of string
  maintain_start_time = null
  # major_version - (required) is a type of string
  major_version = null
  # node_count - (required) is a type of number
  node_count = null
  # password - (optional) is a type of string
  password = null
  # pay_type - (required) is a type of string
  pay_type = null
  # period - (optional) is a type of number
  period = null
  # period_unit - (optional) is a type of string
  period_unit = null
  # security_groups - (optional) is a type of list of string
  security_groups = []
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

variable "cluster_name" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "major_version" {
  description = "(required)"
  type        = string
}

variable "node_count" {
  description = "(required)"
  type        = number
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "alicloud_cassandra_cluster" "this" {
  # auto_renew - (optional) is a type of bool
  auto_renew = var.auto_renew
  # auto_renew_period - (optional) is a type of number
  auto_renew_period = var.auto_renew_period
  # cluster_name - (optional) is a type of string
  cluster_name = var.cluster_name
  # data_center_name - (optional) is a type of string
  data_center_name = var.data_center_name
  # disk_size - (optional) is a type of number
  disk_size = var.disk_size
  # disk_type - (optional) is a type of string
  disk_type = var.disk_type
  # enable_public - (optional) is a type of bool
  enable_public = var.enable_public
  # instance_type - (required) is a type of string
  instance_type = var.instance_type
  # ip_white - (optional) is a type of string
  ip_white = var.ip_white
  # maintain_end_time - (optional) is a type of string
  maintain_end_time = var.maintain_end_time
  # maintain_start_time - (optional) is a type of string
  maintain_start_time = var.maintain_start_time
  # major_version - (required) is a type of string
  major_version = var.major_version
  # node_count - (required) is a type of number
  node_count = var.node_count
  # password - (optional) is a type of string
  password = var.password
  # pay_type - (required) is a type of string
  pay_type = var.pay_type
  # period - (optional) is a type of number
  period = var.period
  # period_unit - (optional) is a type of string
  period_unit = var.period_unit
  # security_groups - (optional) is a type of list of string
  security_groups = var.security_groups
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vswitch_id - (required) is a type of string
  vswitch_id = var.vswitch_id
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id

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
output "id" {
  description = "returns a string"
  value       = alicloud_cassandra_cluster.this.id
}

output "ip_white" {
  description = "returns a string"
  value       = alicloud_cassandra_cluster.this.ip_white
}

output "public_points" {
  description = "returns a list of string"
  value       = alicloud_cassandra_cluster.this.public_points
}

output "security_groups" {
  description = "returns a list of string"
  value       = alicloud_cassandra_cluster.this.security_groups
}

output "status" {
  description = "returns a string"
  value       = alicloud_cassandra_cluster.this.status
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_cassandra_cluster.this.zone_id
}

output "this" {
  value = alicloud_cassandra_cluster.this
}
```

[top](#index)