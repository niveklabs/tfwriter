# nomad_acl_tokens

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
    nomad = ">= 1.4.14"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_acl_tokens" {
  source = "./modules/nomad/d/nomad_acl_tokens"

  # prefix - (optional) is a type of string
  prefix = null
}
```

[top](#index)

### Variables

```terraform
variable "prefix" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nomad_acl_tokens" "this" {
  prefix = var.prefix
}
```

[top](#index)

### Outputs

```terraform
output "acl_tokens" {
  description = "returns a list of object"
  value       = data.nomad_acl_tokens.this.acl_tokens
}

output "id" {
  description = "returns a string"
  value       = data.nomad_acl_tokens.this.id
}

output "this" {
  value = nomad_acl_tokens.this
}
```

[top](#index)