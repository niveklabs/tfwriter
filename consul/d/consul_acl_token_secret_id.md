# consul_acl_token_secret_id

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
module "consul_acl_token_secret_id" {
  source = "./modules/consul/d/consul_acl_token_secret_id"

  # accessor_id - (required) is a type of string
  accessor_id = null
  # pgp_key - (optional) is a type of string
  pgp_key = null
}
```

[top](#index)

### Variables

```terraform
variable "accessor_id" {
  description = "(required)"
  type        = string
}

variable "pgp_key" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "consul_acl_token_secret_id" "this" {
  # accessor_id - (required) is a type of string
  accessor_id = var.accessor_id
  # pgp_key - (optional) is a type of string
  pgp_key = var.pgp_key
}
```

[top](#index)

### Outputs

```terraform
output "encrypted_secret_id" {
  description = "returns a string"
  value       = data.consul_acl_token_secret_id.this.encrypted_secret_id
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = data.consul_acl_token_secret_id.this.id
}

output "secret_id" {
  description = "returns a string"
  value       = data.consul_acl_token_secret_id.this.secret_id
  sensitive   = true
}

output "this" {
  value = consul_acl_token_secret_id.this
}
```

[top](#index)