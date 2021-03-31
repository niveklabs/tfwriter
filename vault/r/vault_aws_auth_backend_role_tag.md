# vault_aws_auth_backend_role_tag

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_aws_auth_backend_role_tag" {
  source = "./modules/vault/r/vault_aws_auth_backend_role_tag"

  # allow_instance_migration - (optional) is a type of bool
  allow_instance_migration = null
  # backend - (optional) is a type of string
  backend = null
  # disallow_reauthentication - (optional) is a type of bool
  disallow_reauthentication = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # max_ttl - (optional) is a type of string
  max_ttl = null
  # policies - (optional) is a type of set of string
  policies = []
  # role - (required) is a type of string
  role = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_instance_migration" {
  description = "(optional) - Allows migration of the underlying instance where the client resides."
  type        = bool
  default     = null
}

variable "backend" {
  description = "(optional) - AWS auth backend to read tags from."
  type        = string
  default     = null
}

variable "disallow_reauthentication" {
  description = "(optional) - Only allow a single token to be granted per instance ID."
  type        = bool
  default     = null
}

variable "instance_id" {
  description = "(optional) - Instance ID for which this tag is intended. The created tag can only be used by the instance with the given ID."
  type        = string
  default     = null
}

variable "max_ttl" {
  description = "(optional) - The maximum allowed lifetime of tokens issued using this role."
  type        = string
  default     = null
}

variable "policies" {
  description = "(optional) - Policies to be associated with the tag."
  type        = set(string)
  default     = null
}

variable "role" {
  description = "(required) - Name of the role."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_aws_auth_backend_role_tag" "this" {
  allow_instance_migration  = var.allow_instance_migration
  backend                   = var.backend
  disallow_reauthentication = var.disallow_reauthentication
  instance_id               = var.instance_id
  max_ttl                   = var.max_ttl
  policies                  = var.policies
  role                      = var.role
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_aws_auth_backend_role_tag.this.id
}

output "tag_key" {
  description = "returns a string"
  value       = vault_aws_auth_backend_role_tag.this.tag_key
}

output "tag_value" {
  description = "returns a string"
  value       = vault_aws_auth_backend_role_tag.this.tag_value
}

output "this" {
  value = vault_aws_auth_backend_role_tag.this
}
```

[top](#index)