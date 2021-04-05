# alicloud_security_group_rule

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
module "alicloud_security_group_rule" {
  source = "./modules/alicloud/r/alicloud_security_group_rule"

  # cidr_ip - (optional) is a type of string
  cidr_ip = null
  # description - (optional) is a type of string
  description = null
  # ip_protocol - (required) is a type of string
  ip_protocol = null
  # nic_type - (optional) is a type of string
  nic_type = null
  # policy - (optional) is a type of string
  policy = null
  # port_range - (optional) is a type of string
  port_range = null
  # priority - (optional) is a type of number
  priority = null
  # security_group_id - (required) is a type of string
  security_group_id = null
  # source_group_owner_account - (optional) is a type of string
  source_group_owner_account = null
  # source_security_group_id - (optional) is a type of string
  source_security_group_id = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "cidr_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_protocol" {
  description = "(required)"
  type        = string
}

variable "nic_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port_range" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_group_id" {
  description = "(required)"
  type        = string
}

variable "source_group_owner_account" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - Type of rule, ingress (inbound) or egress (outbound)."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_security_group_rule" "this" {
  cidr_ip                    = var.cidr_ip
  description                = var.description
  ip_protocol                = var.ip_protocol
  nic_type                   = var.nic_type
  policy                     = var.policy
  port_range                 = var.port_range
  priority                   = var.priority
  security_group_id          = var.security_group_id
  source_group_owner_account = var.source_group_owner_account
  source_security_group_id   = var.source_security_group_id
  type                       = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_security_group_rule.this.id
}

output "nic_type" {
  description = "returns a string"
  value       = alicloud_security_group_rule.this.nic_type
}

output "this" {
  value = alicloud_security_group_rule.this
}
```

[top](#index)