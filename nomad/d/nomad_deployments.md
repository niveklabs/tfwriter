# nomad_deployments

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
module "nomad_deployments" {
  source = "./modules/nomad/d/nomad_deployments"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "nomad_deployments" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "deployments" {
  description = "returns a list of map of string"
  value       = data.nomad_deployments.this.deployments
}

output "id" {
  description = "returns a string"
  value       = data.nomad_deployments.this.id
}

output "this" {
  value = nomad_deployments.this
}
```

[top](#index)