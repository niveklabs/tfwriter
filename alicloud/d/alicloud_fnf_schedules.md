# alicloud_fnf_schedules

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_fnf_schedules" {
  source = "./modules/alicloud/d/alicloud_fnf_schedules"

  # flow_name - (required) is a type of string
  flow_name = null
  # ids - (optional) is a type of list of string
  ids = []
  # limit - (optional) is a type of number
  limit = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "flow_name" {
  description = "(required)"
  type        = string
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "limit" {
  description = "(optional)"
  type        = number
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
```

[top](#index)

### Datasource

```terraform
data "alicloud_fnf_schedules" "this" {
  flow_name   = var.flow_name
  ids         = var.ids
  limit       = var.limit
  name_regex  = var.name_regex
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_fnf_schedules.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_fnf_schedules.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_fnf_schedules.this.names
}

output "schedules" {
  description = "returns a list of object"
  value       = data.alicloud_fnf_schedules.this.schedules
}

output "this" {
  value = alicloud_fnf_schedules.this
}
```

[top](#index)