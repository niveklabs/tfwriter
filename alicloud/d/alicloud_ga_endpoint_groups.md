# alicloud_ga_endpoint_groups

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
module "alicloud_ga_endpoint_groups" {
  source = "./modules/alicloud/d/alicloud_ga_endpoint_groups"

  # accelerator_id - (required) is a type of string
  accelerator_id = null
  # endpoint_group_type - (optional) is a type of string
  endpoint_group_type = null
  # ids - (optional) is a type of list of string
  ids = []
  # listener_id - (optional) is a type of string
  listener_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "accelerator_id" {
  description = "(required)"
  type        = string
}

variable "endpoint_group_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "listener_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
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
data "alicloud_ga_endpoint_groups" "this" {
  # accelerator_id - (required) is a type of string
  accelerator_id = var.accelerator_id
  # endpoint_group_type - (optional) is a type of string
  endpoint_group_type = var.endpoint_group_type
  # ids - (optional) is a type of list of string
  ids = var.ids
  # listener_id - (optional) is a type of string
  listener_id = var.listener_id
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "groups" {
  description = "returns a list of object"
  value       = data.alicloud_ga_endpoint_groups.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_ga_endpoint_groups.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ga_endpoint_groups.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ga_endpoint_groups.this.names
}

output "this" {
  value = alicloud_ga_endpoint_groups.this
}
```

[top](#index)