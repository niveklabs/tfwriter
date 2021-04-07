# nomad_namespace

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
module "nomad_namespace" {
  source = "./modules/nomad/d/nomad_namespace"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "nomad_namespace" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.nomad_namespace.this.description
}

output "id" {
  description = "returns a string"
  value       = data.nomad_namespace.this.id
}

output "quota" {
  description = "returns a string"
  value       = data.nomad_namespace.this.quota
}

output "this" {
  value = nomad_namespace.this
}
```

[top](#index)