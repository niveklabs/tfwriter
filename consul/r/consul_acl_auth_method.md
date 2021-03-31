# consul_acl_auth_method

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
module "consul_acl_auth_method" {
  source = "./modules/consul/r/consul_acl_auth_method"

  # config - (optional) is a type of map of string
  config = {}
  # config_json - (optional) is a type of string
  config_json = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # max_token_ttl - (optional) is a type of string
  max_token_ttl = null
  # name - (required) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
  # token_locality - (optional) is a type of string
  token_locality = null
  # type - (required) is a type of string
  type = null

  namespace_rule = [{
    bind_namespace = null
    selector       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "config" {
  description = "(optional) - The raw configuration for this ACL auth method."
  type        = map(string)
  default     = null
}

variable "config_json" {
  description = "(optional) - The raw configuration for this ACL auth method."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - A free form human readable description of the auth method."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - An optional name to use instead of the name attribute when displaying information about this auth method."
  type        = string
  default     = null
}

variable "max_token_ttl" {
  description = "(optional) - The maximum life of any token created by this auth method."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the ACL auth method."
  type        = string
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "token_locality" {
  description = "(optional) - The kind of token that this auth method produces. This can be either 'local' or 'global'."
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - The type of the ACL auth method."
  type        = string
}

variable "namespace_rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bind_namespace = string
      selector       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "consul_acl_auth_method" "this" {
  config         = var.config
  config_json    = var.config_json
  description    = var.description
  display_name   = var.display_name
  max_token_ttl  = var.max_token_ttl
  name           = var.name
  namespace      = var.namespace
  token_locality = var.token_locality
  type           = var.type

  dynamic "namespace_rule" {
    for_each = var.namespace_rule
    content {
      bind_namespace = namespace_rule.value["bind_namespace"]
      selector       = namespace_rule.value["selector"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = consul_acl_auth_method.this.id
}

output "this" {
  value = consul_acl_auth_method.this
}
```

[top](#index)