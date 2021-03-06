# mongodbatlas_network_containers

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
module "mongodbatlas_network_containers" {
  source = "./modules/mongodbatlas/d/mongodbatlas_network_containers"

  # project_id - (required) is a type of string
  project_id = null
  # provider_name - (required) is a type of string
  provider_name = null
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(required)"
  type        = string
}

variable "provider_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_network_containers" "this" {
  # project_id - (required) is a type of string
  project_id = var.project_id
  # provider_name - (required) is a type of string
  provider_name = var.provider_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_network_containers.this.id
}

output "results" {
  description = "returns a list of object"
  value       = data.mongodbatlas_network_containers.this.results
}

output "this" {
  value = mongodbatlas_network_containers.this
}
```

[top](#index)