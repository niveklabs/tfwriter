# nomad_acl_policy

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
module "nomad_acl_policy" {
  source = "./modules/nomad/d/nomad_acl_policy"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "nomad_acl_policy" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.nomad_acl_policy.this.description
}

output "id" {
  description = "returns a string"
  value       = data.nomad_acl_policy.this.id
}

output "rules" {
  description = "returns a string"
  value       = data.nomad_acl_policy.this.rules
}

output "this" {
  value = nomad_acl_policy.this
}
```

[top](#index)