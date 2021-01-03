# fortios_authentication_rule

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_authentication_rule" {
  source = "./modules/fortios/r/fortios_authentication_rule"

  # active_auth_method - (optional) is a type of string
  active_auth_method = null
  # comments - (optional) is a type of string
  comments = null
  # ip_based - (optional) is a type of string
  ip_based = null
  # name - (optional) is a type of string
  name = null
  # protocol - (optional) is a type of string
  protocol = null
  # sso_auth_method - (optional) is a type of string
  sso_auth_method = null
  # status - (optional) is a type of string
  status = null
  # transaction_based - (optional) is a type of string
  transaction_based = null
  # web_auth_cookie - (optional) is a type of string
  web_auth_cookie = null

  srcaddr = [{
    name = null
  }]

  srcaddr6 = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "active_auth_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_based" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sso_auth_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "transaction_based" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "web_auth_cookie" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "srcaddr" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "srcaddr6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_authentication_rule" "this" {
  active_auth_method = var.active_auth_method
  comments           = var.comments
  ip_based           = var.ip_based
  name               = var.name
  protocol           = var.protocol
  sso_auth_method    = var.sso_auth_method
  status             = var.status
  transaction_based  = var.transaction_based
  web_auth_cookie    = var.web_auth_cookie

  dynamic "srcaddr" {
    for_each = var.srcaddr
    content {
      name = srcaddr.value["name"]
    }
  }

  dynamic "srcaddr6" {
    for_each = var.srcaddr6
    content {
      name = srcaddr6.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "active_auth_method" {
  description = "returns a string"
  value       = fortios_authentication_rule.this.active_auth_method
}

output "id" {
  description = "returns a string"
  value       = fortios_authentication_rule.this.id
}

output "ip_based" {
  description = "returns a string"
  value       = fortios_authentication_rule.this.ip_based
}

output "name" {
  description = "returns a string"
  value       = fortios_authentication_rule.this.name
}

output "protocol" {
  description = "returns a string"
  value       = fortios_authentication_rule.this.protocol
}

output "sso_auth_method" {
  description = "returns a string"
  value       = fortios_authentication_rule.this.sso_auth_method
}

output "status" {
  description = "returns a string"
  value       = fortios_authentication_rule.this.status
}

output "transaction_based" {
  description = "returns a string"
  value       = fortios_authentication_rule.this.transaction_based
}

output "web_auth_cookie" {
  description = "returns a string"
  value       = fortios_authentication_rule.this.web_auth_cookie
}

output "this" {
  value = fortios_authentication_rule.this
}
```

[top](#index)