# alicloud_ga_accelerators

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
module "alicloud_ga_accelerators" {
  source = "./modules/alicloud/d/alicloud_ga_accelerators"

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
data "alicloud_ga_accelerators" "this" {
  ids         = var.ids
  name_regex  = var.name_regex
  output_file = var.output_file
  status      = var.status
}
```

[top](#index)

### Outputs

```terraform
output "accelerators" {
  description = "returns a list of object"
  value       = data.alicloud_ga_accelerators.this.accelerators
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_ga_accelerators.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ga_accelerators.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ga_accelerators.this.names
}

output "this" {
  value = alicloud_ga_accelerators.this
}
```

[top](#index)