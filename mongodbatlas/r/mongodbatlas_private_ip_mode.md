# mongodbatlas_private_ip_mode

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "mongodbatlas_private_ip_mode" {
  source = "./modules/mongodbatlas/r/mongodbatlas_private_ip_mode"

  # enabled - (required) is a type of bool
  enabled = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(required)"
  type        = bool
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_private_ip_mode" "this" {
  # enabled - (required) is a type of bool
  enabled = var.enabled
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mongodbatlas_private_ip_mode.this.id
}

output "this" {
  value = mongodbatlas_private_ip_mode.this
}
```

[top](#index)