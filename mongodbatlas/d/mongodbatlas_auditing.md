# mongodbatlas_auditing

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
module "mongodbatlas_auditing" {
  source = "./modules/mongodbatlas/d/mongodbatlas_auditing"

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
data "mongodbatlas_auditing" "this" {
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "audit_authorization_success" {
  description = "returns a bool"
  value       = data.mongodbatlas_auditing.this.audit_authorization_success
}

output "audit_filter" {
  description = "returns a string"
  value       = data.mongodbatlas_auditing.this.audit_filter
}

output "configuration_type" {
  description = "returns a string"
  value       = data.mongodbatlas_auditing.this.configuration_type
}

output "enabled" {
  description = "returns a bool"
  value       = data.mongodbatlas_auditing.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_auditing.this.id
}

output "this" {
  value = mongodbatlas_auditing.this
}
```

[top](#index)