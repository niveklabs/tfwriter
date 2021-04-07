# alicloud_ram_groups

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
module "alicloud_ram_groups" {
  source = "./modules/alicloud/d/alicloud_ram_groups"

  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # policy_name - (optional) is a type of string
  policy_name = null
  # policy_type - (optional) is a type of string
  policy_type = null
  # user_name - (optional) is a type of string
  user_name = null
}
```

[top](#index)

### Variables

```terraform
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

variable "policy_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ram_groups" "this" {
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # policy_name - (optional) is a type of string
  policy_name = var.policy_name
  # policy_type - (optional) is a type of string
  policy_type = var.policy_type
  # user_name - (optional) is a type of string
  user_name = var.user_name
}
```

[top](#index)

### Outputs

```terraform
output "groups" {
  description = "returns a list of object"
  value       = data.alicloud_ram_groups.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_ram_groups.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ram_groups.this.names
}

output "this" {
  value = alicloud_ram_groups.this
}
```

[top](#index)