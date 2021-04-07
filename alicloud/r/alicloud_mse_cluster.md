# alicloud_mse_cluster

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
module "alicloud_mse_cluster" {
  source = "./modules/alicloud/r/alicloud_mse_cluster"

  # acl_entry_list - (optional) is a type of set of string
  acl_entry_list = []
  # cluster_alias_name - (optional) is a type of string
  cluster_alias_name = null
  # cluster_specification - (required) is a type of string
  cluster_specification = null
  # cluster_type - (required) is a type of string
  cluster_type = null
  # cluster_version - (required) is a type of string
  cluster_version = null
  # disk_type - (optional) is a type of string
  disk_type = null
  # instance_count - (required) is a type of number
  instance_count = null
  # net_type - (required) is a type of string
  net_type = null
  # private_slb_specification - (optional) is a type of string
  private_slb_specification = null
  # pub_network_flow - (optional) is a type of string
  pub_network_flow = null
  # pub_slb_specification - (optional) is a type of string
  pub_slb_specification = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acl_entry_list" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "cluster_alias_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cluster_specification" {
  description = "(required)"
  type        = string
}

variable "cluster_type" {
  description = "(required)"
  type        = string
}

variable "cluster_version" {
  description = "(required)"
  type        = string
}

variable "disk_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_count" {
  description = "(required)"
  type        = number
}

variable "net_type" {
  description = "(required)"
  type        = string
}

variable "private_slb_specification" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pub_network_flow" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pub_slb_specification" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_id" {
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_mse_cluster" "this" {
  # acl_entry_list - (optional) is a type of set of string
  acl_entry_list = var.acl_entry_list
  # cluster_alias_name - (optional) is a type of string
  cluster_alias_name = var.cluster_alias_name
  # cluster_specification - (required) is a type of string
  cluster_specification = var.cluster_specification
  # cluster_type - (required) is a type of string
  cluster_type = var.cluster_type
  # cluster_version - (required) is a type of string
  cluster_version = var.cluster_version
  # disk_type - (optional) is a type of string
  disk_type = var.disk_type
  # instance_count - (required) is a type of number
  instance_count = var.instance_count
  # net_type - (required) is a type of string
  net_type = var.net_type
  # private_slb_specification - (optional) is a type of string
  private_slb_specification = var.private_slb_specification
  # pub_network_flow - (optional) is a type of string
  pub_network_flow = var.pub_network_flow
  # pub_slb_specification - (optional) is a type of string
  pub_slb_specification = var.pub_slb_specification
  # vswitch_id - (optional) is a type of string
  vswitch_id = var.vswitch_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_mse_cluster.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_mse_cluster.this.status
}

output "this" {
  value = alicloud_mse_cluster.this
}
```

[top](#index)