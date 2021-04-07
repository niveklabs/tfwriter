# nomad_regions

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
module "nomad_regions" {
  source = "./modules/nomad/d/nomad_regions"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "nomad_regions" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.nomad_regions.this.id
}

output "regions" {
  description = "returns a list of string"
  value       = data.nomad_regions.this.regions
}

output "this" {
  value = nomad_regions.this
}
```

[top](#index)