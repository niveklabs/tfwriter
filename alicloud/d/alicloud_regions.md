# alicloud_regions

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
module "alicloud_regions" {
  source = "./modules/alicloud/d/alicloud_regions"

  # current - (optional) is a type of bool
  current = null
  # name - (optional) is a type of string
  name = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "current" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
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
data "alicloud_regions" "this" {
  current     = var.current
  name        = var.name
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "current" {
  description = "returns a bool"
  value       = data.alicloud_regions.this.current
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_regions.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_regions.this.ids
}

output "name" {
  description = "returns a string"
  value       = data.alicloud_regions.this.name
}

output "regions" {
  description = "returns a list of object"
  value       = data.alicloud_regions.this.regions
}

output "this" {
  value = alicloud_regions.this
}
```

[top](#index)