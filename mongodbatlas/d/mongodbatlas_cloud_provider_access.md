# mongodbatlas_cloud_provider_access

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
module "mongodbatlas_cloud_provider_access" {
  source = "./modules/mongodbatlas/d/mongodbatlas_cloud_provider_access"

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
data "mongodbatlas_cloud_provider_access" "this" {
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "aws_iam_roles" {
  description = "returns a list of object"
  value       = data.mongodbatlas_cloud_provider_access.this.aws_iam_roles
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_cloud_provider_access.this.id
}

output "this" {
  value = mongodbatlas_cloud_provider_access.this
}
```

[top](#index)