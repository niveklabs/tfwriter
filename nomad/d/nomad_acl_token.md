# nomad_acl_token

[back](../nomad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/nomad/d/nomad_acl_token"

  # accessor_id - (required) is a type of string
  accessor_id = null
}
```

[top](#index)

### Variables

```terraform
variable "accessor_id" {
  description = "(required) - Non-sensitive identifier for this token."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "nomad_acl_token" "this" {
  accessor_id = var.accessor_id
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = data.nomad_acl_token.this.create_time
}

output "global" {
  description = "returns a bool"
  value       = data.nomad_acl_token.this.global
}

output "id" {
  description = "returns a string"
  value       = data.nomad_acl_token.this.id
}

output "name" {
  description = "returns a string"
  value       = data.nomad_acl_token.this.name
}

output "policies" {
  description = "returns a set of string"
  value       = data.nomad_acl_token.this.policies
}

output "secret_id" {
  description = "returns a string"
  value       = data.nomad_acl_token.this.secret_id
  sensitive   = true
}

output "type" {
  description = "returns a string"
  value       = data.nomad_acl_token.this.type
}

output "this" {
  value = nomad_acl_token.this
}
```

[top](#index)