# mongodbatlas_auditing

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
    mongodbatlas = ">= 0.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_auditing" {
  source = "./modules/mongodbatlas/r/mongodbatlas_auditing"

  # audit_authorization_success - (optional) is a type of bool
  audit_authorization_success = null
  # audit_filter - (optional) is a type of string
  audit_filter = null
  # enabled - (optional) is a type of bool
  enabled = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "audit_authorization_success" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "audit_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_auditing" "this" {
  audit_authorization_success = var.audit_authorization_success
  audit_filter                = var.audit_filter
  enabled                     = var.enabled
  project_id                  = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "audit_authorization_success" {
  description = "returns a bool"
  value       = mongodbatlas_auditing.this.audit_authorization_success
}

output "audit_filter" {
  description = "returns a string"
  value       = mongodbatlas_auditing.this.audit_filter
}

output "configuration_type" {
  description = "returns a string"
  value       = mongodbatlas_auditing.this.configuration_type
}

output "enabled" {
  description = "returns a bool"
  value       = mongodbatlas_auditing.this.enabled
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_auditing.this.id
}

output "this" {
  value = mongodbatlas_auditing.this
}
```

[top](#index)