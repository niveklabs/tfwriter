# nomad_acl_token

[back](../nomad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nomad = ">= 1.4.11"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_acl_token" {
  source = "./modules/nomad/r/nomad_acl_token"

  # global - (optional) is a type of bool
  global = null
  # name - (optional) is a type of string
  name = null
  # policies - (optional) is a type of set of string
  policies = []
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "global" {
  description = "(optional) - Whether the token should be replicated to all regions or not."
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - Human-readable name for this token."
  type        = string
  default     = null
}

variable "policies" {
  description = "(optional) - The ACL policies to associate with the token, if it's a 'client' type."
  type        = set(string)
  default     = null
}

variable "type" {
  description = "(required) - The type of token to create, 'client' or 'management'."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "nomad_acl_token" "this" {
  global   = var.global
  name     = var.name
  policies = var.policies
  type     = var.type
}
```

[top](#index)

### Outputs

```terraform
output "accessor_id" {
  description = "returns a string"
  value       = nomad_acl_token.this.accessor_id
}

output "create_time" {
  description = "returns a string"
  value       = nomad_acl_token.this.create_time
}

output "id" {
  description = "returns a string"
  value       = nomad_acl_token.this.id
}

output "secret_id" {
  description = "returns a string"
  value       = nomad_acl_token.this.secret_id
  sensitive   = true
}

output "this" {
  value = nomad_acl_token.this
}
```

[top](#index)