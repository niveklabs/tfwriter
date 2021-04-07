# alicloud_nas_access_rule

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "alicloud_nas_access_rule" {
  source = "./modules/alicloud/r/alicloud_nas_access_rule"

  # access_group_name - (required) is a type of string
  access_group_name = null
  # priority - (optional) is a type of number
  priority = null
  # rw_access_type - (optional) is a type of string
  rw_access_type = null
  # source_cidr_ip - (required) is a type of string
  source_cidr_ip = null
  # user_access_type - (optional) is a type of string
  user_access_type = null
}
```

[top](#index)

### Variables

```terraform
variable "access_group_name" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rw_access_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_cidr_ip" {
  description = "(required)"
  type        = string
}

variable "user_access_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_nas_access_rule" "this" {
  # access_group_name - (required) is a type of string
  access_group_name = var.access_group_name
  # priority - (optional) is a type of number
  priority = var.priority
  # rw_access_type - (optional) is a type of string
  rw_access_type = var.rw_access_type
  # source_cidr_ip - (required) is a type of string
  source_cidr_ip = var.source_cidr_ip
  # user_access_type - (optional) is a type of string
  user_access_type = var.user_access_type
}
```

[top](#index)

### Outputs

```terraform
output "access_rule_id" {
  description = "returns a string"
  value       = alicloud_nas_access_rule.this.access_rule_id
}

output "id" {
  description = "returns a string"
  value       = alicloud_nas_access_rule.this.id
}

output "this" {
  value = alicloud_nas_access_rule.this
}
```

[top](#index)