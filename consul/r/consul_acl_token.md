# consul_acl_token

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
    consul = ">= 2.10.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_acl_token" {
  source = "./modules/consul/r/consul_acl_token"

  # accessor_id - (optional) is a type of string
  accessor_id = null
  # description - (optional) is a type of string
  description = null
  # local - (optional) is a type of bool
  local = null
  # namespace - (optional) is a type of string
  namespace = null
  # policies - (optional) is a type of set of string
  policies = []
  # roles - (optional) is a type of set of string
  roles = []
}
```

[top](#index)

### Variables

```terraform
variable "accessor_id" {
  description = "(optional) - The token id."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - The token description."
  type        = string
  default     = null
}

variable "local" {
  description = "(optional) - Flag to set the token local to the current datacenter."
  type        = bool
  default     = null
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policies" {
  description = "(optional) - List of policies."
  type        = set(string)
  default     = null
}

variable "roles" {
  description = "(optional) - List of roles"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "consul_acl_token" "this" {
  accessor_id = var.accessor_id
  description = var.description
  local       = var.local
  namespace   = var.namespace
  policies    = var.policies
  roles       = var.roles
}
```

[top](#index)

### Outputs

```terraform
output "accessor_id" {
  description = "returns a string"
  value       = consul_acl_token.this.accessor_id
}

output "id" {
  description = "returns a string"
  value       = consul_acl_token.this.id
}

output "this" {
  value = consul_acl_token.this
}
```

[top](#index)