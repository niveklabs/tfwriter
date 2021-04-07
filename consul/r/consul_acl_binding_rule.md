# consul_acl_binding_rule

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    consul = ">= 2.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_acl_binding_rule" {
  source = "./modules/consul/r/consul_acl_binding_rule"

  # auth_method - (required) is a type of string
  auth_method = null
  # bind_name - (required) is a type of string
  bind_name = null
  # bind_type - (required) is a type of string
  bind_type = null
  # description - (optional) is a type of string
  description = null
  # namespace - (optional) is a type of string
  namespace = null
  # selector - (optional) is a type of string
  selector = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_method" {
  description = "(required) - The name of the ACL auth method this rule apply."
  type        = string
}

variable "bind_name" {
  description = "(required) - The name to bind to a token at login-time."
  type        = string
}

variable "bind_type" {
  description = "(required) - Specifies the way the binding rule affects a token created at login."
  type        = string
}

variable "description" {
  description = "(optional) - A free form human readable description of the binding rule."
  type        = string
  default     = null
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "selector" {
  description = "(optional) - The expression used to math this rule against valid identities returned from an auth method validation."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "consul_acl_binding_rule" "this" {
  # auth_method - (required) is a type of string
  auth_method = var.auth_method
  # bind_name - (required) is a type of string
  bind_name = var.bind_name
  # bind_type - (required) is a type of string
  bind_type = var.bind_type
  # description - (optional) is a type of string
  description = var.description
  # namespace - (optional) is a type of string
  namespace = var.namespace
  # selector - (optional) is a type of string
  selector = var.selector
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = consul_acl_binding_rule.this.id
}

output "this" {
  value = consul_acl_binding_rule.this
}
```

[top](#index)