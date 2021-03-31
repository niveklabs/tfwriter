# alicloud_ram_policies

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
module "alicloud_ram_policies" {
  source = "./modules/alicloud/d/alicloud_ram_policies"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # group_name - (optional) is a type of string
  group_name = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # role_name - (optional) is a type of string
  role_name = null
  # type - (optional) is a type of string
  type = null
  # user_name - (optional) is a type of string
  user_name = null
}
```

[top](#index)

### Variables

```terraform
variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

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

variable "role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
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
data "alicloud_ram_policies" "this" {
  enable_details = var.enable_details
  group_name     = var.group_name
  ids            = var.ids
  name_regex     = var.name_regex
  output_file    = var.output_file
  role_name      = var.role_name
  type           = var.type
  user_name      = var.user_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ram_policies.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ram_policies.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ram_policies.this.names
}

output "policies" {
  description = "returns a list of object"
  value       = data.alicloud_ram_policies.this.policies
}

output "this" {
  value = alicloud_ram_policies.this
}
```

[top](#index)