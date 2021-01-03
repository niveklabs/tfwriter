# alicloud_ram_users

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
module "alicloud_ram_users" {
  source = "./modules/alicloud/d/alicloud_ram_users"

  # group_name - (optional) is a type of string
  group_name = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # policy_name - (optional) is a type of string
  policy_name = null
  # policy_type - (optional) is a type of string
  policy_type = null
}
```

[top](#index)

### Variables

```terraform
variable "group_name" {
  description = "(optional)"
  type        = string
  default     = null
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
```

[top](#index)

### Datasource

```terraform
data "alicloud_ram_users" "this" {
  group_name  = var.group_name
  ids         = var.ids
  name_regex  = var.name_regex
  output_file = var.output_file
  policy_name = var.policy_name
  policy_type = var.policy_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ram_users.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ram_users.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ram_users.this.names
}

output "users" {
  description = "returns a list of object"
  value       = data.alicloud_ram_users.this.users
}

output "this" {
  value = alicloud_ram_users.this
}
```

[top](#index)