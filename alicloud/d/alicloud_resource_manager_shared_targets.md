# alicloud_resource_manager_shared_targets

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_resource_manager_shared_targets" {
  source = "./modules/alicloud/d/alicloud_resource_manager_shared_targets"

  # ids - (optional) is a type of list of string
  ids = []
  # output_file - (optional) is a type of string
  output_file = null
  # resource_share_id - (optional) is a type of string
  resource_share_id = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_share_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_resource_manager_shared_targets" "this" {
  # ids - (optional) is a type of list of string
  ids = var.ids
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # resource_share_id - (optional) is a type of string
  resource_share_id = var.resource_share_id
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_resource_manager_shared_targets.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_resource_manager_shared_targets.this.ids
}

output "targets" {
  description = "returns a list of object"
  value       = data.alicloud_resource_manager_shared_targets.this.targets
}

output "this" {
  value = alicloud_resource_manager_shared_targets.this
}
```

[top](#index)