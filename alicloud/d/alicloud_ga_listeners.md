# alicloud_ga_listeners

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
module "alicloud_ga_listeners" {
  source = "./modules/alicloud/d/alicloud_ga_listeners"

  # accelerator_id - (required) is a type of string
  accelerator_id = null
  # ids - (optional) is a type of list of string
  ids = []
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

variable "ids" {
  description = "(optional)"
  type        = list(string)
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
data "alicloud_ga_listeners" "this" {
  # accelerator_id - (required) is a type of string
  accelerator_id = var.accelerator_id
  # ids - (optional) is a type of list of string
  ids = var.ids
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
output "id" {
  description = "returns a string"
  value       = data.alicloud_ga_listeners.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ga_listeners.this.ids
}

output "listeners" {
  description = "returns a list of object"
  value       = data.alicloud_ga_listeners.this.listeners
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ga_listeners.this.names
}

output "this" {
  value = alicloud_ga_listeners.this
}
```

[top](#index)