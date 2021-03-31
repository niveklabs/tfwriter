# mongodbatlas_network_peerings

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mongodbatlas = ">= 0.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_network_peerings" {
  source = "./modules/mongodbatlas/d/mongodbatlas_network_peerings"

  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_network_peerings" "this" {
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_peerings.this.id
}

output "results" {
  description = "returns a list of object"
  value       = data.mongodbatlas_network_peerings.this.results
}

output "this" {
  value = mongodbatlas_network_peerings.this
}
```

[top](#index)