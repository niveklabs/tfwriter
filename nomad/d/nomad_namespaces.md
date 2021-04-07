# nomad_namespaces

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
module "nomad_namespaces" {
  source = "./modules/nomad/d/nomad_namespaces"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "nomad_namespaces" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.nomad_namespaces.this.id
}

output "namespaces" {
  description = "returns a list of string"
  value       = data.nomad_namespaces.this.namespaces
}

output "this" {
  value = nomad_namespaces.this
}
```

[top](#index)