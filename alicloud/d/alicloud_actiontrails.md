# alicloud_actiontrails

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
module "alicloud_actiontrails" {
  source = "./modules/alicloud/d/alicloud_actiontrails"

  # ids - (optional) is a type of list of string
  ids = []
  # include_organization_trail - (optional) is a type of bool
  include_organization_trail = null
  # include_shadow_trails - (optional) is a type of bool
  include_shadow_trails = null
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

variable "include_organization_trail" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "include_shadow_trails" {
  description = "(optional)"
  type        = bool
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
data "alicloud_actiontrails" "this" {
  # ids - (optional) is a type of list of string
  ids = var.ids
  # include_organization_trail - (optional) is a type of bool
  include_organization_trail = var.include_organization_trail
  # include_shadow_trails - (optional) is a type of bool
  include_shadow_trails = var.include_shadow_trails
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
output "actiontrails" {
  description = "returns a list of object"
  value       = data.alicloud_actiontrails.this.actiontrails
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_actiontrails.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_actiontrails.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_actiontrails.this.names
}

output "trails" {
  description = "returns a list of object"
  value       = data.alicloud_actiontrails.this.trails
}

output "this" {
  value = alicloud_actiontrails.this
}
```

[top](#index)