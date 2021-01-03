# alicloud_ess_scaling_rules

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
module "alicloud_ess_scaling_rules" {
  source = "./modules/alicloud/d/alicloud_ess_scaling_rules"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # scaling_group_id - (optional) is a type of string
  scaling_group_id = null
  # type - (optional) is a type of string
  type = null
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

variable "scaling_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ess_scaling_rules" "this" {
  ids              = var.ids
  name_regex       = var.name_regex
  output_file      = var.output_file
  scaling_group_id = var.scaling_group_id
  type             = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ess_scaling_rules.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ess_scaling_rules.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ess_scaling_rules.this.names
}

output "rules" {
  description = "returns a list of object"
  value       = data.alicloud_ess_scaling_rules.this.rules
}

output "this" {
  value = alicloud_ess_scaling_rules.this
}
```

[top](#index)