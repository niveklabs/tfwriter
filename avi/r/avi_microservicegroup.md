# avi_microservicegroup

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_microservicegroup" {
  source = "./modules/avi/r/avi_microservicegroup"

  # created_by - (optional) is a type of string
  created_by = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # service_refs - (optional) is a type of list of string
  service_refs = []
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "service_refs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "avi_microservicegroup" "this" {
  # created_by - (optional) is a type of string
  created_by = var.created_by
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # service_refs - (optional) is a type of list of string
  service_refs = var.service_refs
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "created_by" {
  description = "returns a string"
  value       = avi_microservicegroup.this.created_by
}

output "description" {
  description = "returns a string"
  value       = avi_microservicegroup.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_microservicegroup.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_microservicegroup.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_microservicegroup.this.uuid
}

output "this" {
  value = avi_microservicegroup.this
}
```

[top](#index)