# mongodbatlas_third_party_integrations

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
module "mongodbatlas_third_party_integrations" {
  source = "./modules/mongodbatlas/d/mongodbatlas_third_party_integrations"

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
data "mongodbatlas_third_party_integrations" "this" {
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_third_party_integrations.this.id
}

output "results" {
  description = "returns a list of object"
  value       = data.mongodbatlas_third_party_integrations.this.results
}

output "this" {
  value = mongodbatlas_third_party_integrations.this
}
```

[top](#index)