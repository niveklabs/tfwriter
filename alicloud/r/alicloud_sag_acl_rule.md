# alicloud_sag_acl_rule

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_sag_acl_rule" {
  source = "./modules/alicloud/r/alicloud_sag_acl_rule"

  # acl_id - (required) is a type of string
  acl_id = null
  # description - (optional) is a type of string
  description = null
  # dest_cidr - (required) is a type of string
  dest_cidr = null
  # dest_port_range - (required) is a type of string
  dest_port_range = null
  # direction - (required) is a type of string
  direction = null
  # ip_protocol - (required) is a type of string
  ip_protocol = null
  # policy - (required) is a type of string
  policy = null
  # priority - (optional) is a type of number
  priority = null
  # source_cidr - (required) is a type of string
  source_cidr = null
  # source_port_range - (required) is a type of string
  source_port_range = null
}
```

[top](#index)

### Variables

```terraform
variable "acl_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dest_cidr" {
  description = "(required)"
  type        = string
}

variable "dest_port_range" {
  description = "(required)"
  type        = string
}

variable "direction" {
  description = "(required)"
  type        = string
}

variable "ip_protocol" {
  description = "(required)"
  type        = string
}

variable "policy" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "source_cidr" {
  description = "(required)"
  type        = string
}

variable "source_port_range" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_sag_acl_rule" "this" {
  acl_id            = var.acl_id
  description       = var.description
  dest_cidr         = var.dest_cidr
  dest_port_range   = var.dest_port_range
  direction         = var.direction
  ip_protocol       = var.ip_protocol
  policy            = var.policy
  priority          = var.priority
  source_cidr       = var.source_cidr
  source_port_range = var.source_port_range
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_sag_acl_rule.this.id
}

output "this" {
  value = alicloud_sag_acl_rule.this
}
```

[top](#index)