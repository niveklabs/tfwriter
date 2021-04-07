# consul_acl_auth_method

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "consul_acl_auth_method" {
  source = "./modules/consul/d/consul_acl_auth_method"

  # name - (required) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "consul_acl_auth_method" "this" {
  # name - (required) is a type of string
  name = var.name
  # namespace - (optional) is a type of string
  namespace = var.namespace
}
```

[top](#index)

### Outputs

```terraform
output "config" {
  description = "returns a map of string"
  value       = data.consul_acl_auth_method.this.config
}

output "config_json" {
  description = "returns a string"
  value       = data.consul_acl_auth_method.this.config_json
}

output "description" {
  description = "returns a string"
  value       = data.consul_acl_auth_method.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.consul_acl_auth_method.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.consul_acl_auth_method.this.id
}

output "max_token_ttl" {
  description = "returns a string"
  value       = data.consul_acl_auth_method.this.max_token_ttl
}

output "namespace_rule" {
  description = "returns a list of object"
  value       = data.consul_acl_auth_method.this.namespace_rule
}

output "token_locality" {
  description = "returns a string"
  value       = data.consul_acl_auth_method.this.token_locality
}

output "type" {
  description = "returns a string"
  value       = data.consul_acl_auth_method.this.type
}

output "this" {
  value = consul_acl_auth_method.this
}
```

[top](#index)