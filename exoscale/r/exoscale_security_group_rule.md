# exoscale_security_group_rule

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_security_group_rule" {
  source = "./modules/exoscale/r/exoscale_security_group_rule"

  # cidr - (optional) is a type of string
  cidr = null
  # description - (optional) is a type of string
  description = null
  # end_port - (optional) is a type of number
  end_port = null
  # icmp_code - (optional) is a type of number
  icmp_code = null
  # icmp_type - (optional) is a type of number
  icmp_type = null
  # protocol - (optional) is a type of string
  protocol = null
  # security_group - (optional) is a type of string
  security_group = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # start_port - (optional) is a type of number
  start_port = null
  # type - (required) is a type of string
  type = null
  # user_security_group - (optional) is a type of string
  user_security_group = null
  # user_security_group_id - (optional) is a type of string
  user_security_group_id = null

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "icmp_code" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "icmp_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "user_security_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "exoscale_security_group_rule" "this" {
  cidr                   = var.cidr
  description            = var.description
  end_port               = var.end_port
  icmp_code              = var.icmp_code
  icmp_type              = var.icmp_type
  protocol               = var.protocol
  security_group         = var.security_group
  security_group_id      = var.security_group_id
  start_port             = var.start_port
  type                   = var.type
  user_security_group    = var.user_security_group
  user_security_group_id = var.user_security_group_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = exoscale_security_group_rule.this.id
}

output "security_group" {
  description = "returns a string"
  value       = exoscale_security_group_rule.this.security_group
}

output "security_group_id" {
  description = "returns a string"
  value       = exoscale_security_group_rule.this.security_group_id
}

output "user_security_group" {
  description = "returns a string"
  value       = exoscale_security_group_rule.this.user_security_group
}

output "this" {
  value = exoscale_security_group_rule.this
}
```

[top](#index)