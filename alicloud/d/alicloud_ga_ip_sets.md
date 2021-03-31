# alicloud_ga_ip_sets

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ga_ip_sets" {
  source = "./modules/alicloud/d/alicloud_ga_ip_sets"

  # accelerator_id - (required) is a type of string
  accelerator_id = null
  # ids - (optional) is a type of list of string
  ids = []
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
data "alicloud_ga_ip_sets" "this" {
  accelerator_id = var.accelerator_id
  ids            = var.ids
  output_file    = var.output_file
  status         = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ga_ip_sets.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ga_ip_sets.this.ids
}

output "sets" {
  description = "returns a list of object"
  value       = data.alicloud_ga_ip_sets.this.sets
}

output "this" {
  value = alicloud_ga_ip_sets.this
}
```

[top](#index)