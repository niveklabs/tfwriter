# alicloud_security_group_rules

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
module "alicloud_security_group_rules" {
  source = "./modules/alicloud/d/alicloud_security_group_rules"

  # direction - (optional) is a type of string
  direction = null
  # group_id - (required) is a type of string
  group_id = null
  # ip_protocol - (optional) is a type of string
  ip_protocol = null
  # nic_type - (optional) is a type of string
  nic_type = null
  # output_file - (optional) is a type of string
  output_file = null
  # policy - (optional) is a type of string
  policy = null
}
```

[top](#index)

### Variables

```terraform
variable "direction" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
  description = "(required)"
  type        = string
}

variable "ip_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nic_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_security_group_rules" "this" {
  direction   = var.direction
  group_id    = var.group_id
  ip_protocol = var.ip_protocol
  nic_type    = var.nic_type
  output_file = var.output_file
  policy      = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "group_desc" {
  description = "returns a string"
  value       = data.alicloud_security_group_rules.this.group_desc
}

output "group_name" {
  description = "returns a string"
  value       = data.alicloud_security_group_rules.this.group_name
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_security_group_rules.this.id
}

output "rules" {
  description = "returns a list of object"
  value       = data.alicloud_security_group_rules.this.rules
}

output "this" {
  value = alicloud_security_group_rules.this
}
```

[top](#index)