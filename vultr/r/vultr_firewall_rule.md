# vultr_firewall_rule

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_firewall_rule" {
  source = null

  # firewall_group_id - (required) is a type of string
  firewall_group_id = null
  # ip_type - (required) is a type of string
  ip_type = null
  # notes - (optional) is a type of string
  notes = null
  # port - (optional) is a type of string
  port = null
  # protocol - (required) is a type of string
  protocol = null
  # source - (optional) is a type of string
  # subnet - (required) is a type of string
  subnet = null
  # subnet_size - (required) is a type of number
  subnet_size = null
}
```

[top](#index)

### Variables

```terraform
variable "firewall_group_id" {
  description = "(required)"
  type        = string
}

variable "ip_type" {
  description = "(required)"
  type        = string
}

variable "notes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet" {
  description = "(required)"
  type        = string
}

variable "subnet_size" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "vultr_firewall_rule" "this" {
  # firewall_group_id - (required) is a type of string
  firewall_group_id = var.firewall_group_id
  # ip_type - (required) is a type of string
  ip_type = var.ip_type
  # notes - (optional) is a type of string
  notes = var.notes
  # port - (optional) is a type of string
  port = var.port
  # protocol - (required) is a type of string
  protocol = var.protocol
  # source - (optional) is a type of string
  source = var.source
  # subnet - (required) is a type of string
  subnet = var.subnet
  # subnet_size - (required) is a type of number
  subnet_size = var.subnet_size
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vultr_firewall_rule.this.id
}

output "this" {
  value = vultr_firewall_rule.this
}
```

[top](#index)