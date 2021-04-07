# avi_image

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "avi_image" {
  source = "./modules/avi/d/avi_image"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
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

### Datasource

```terraform
data "avi_image" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "controller_info" {
  description = "returns a set of object"
  value       = data.avi_image.this.controller_info
}

output "controller_patch_uuid" {
  description = "returns a string"
  value       = data.avi_image.this.controller_patch_uuid
}

output "id" {
  description = "returns a string"
  value       = data.avi_image.this.id
}

output "migrations" {
  description = "returns a set of object"
  value       = data.avi_image.this.migrations
}

output "name" {
  description = "returns a string"
  value       = data.avi_image.this.name
}

output "se_info" {
  description = "returns a set of object"
  value       = data.avi_image.this.se_info
}

output "se_patch_uuid" {
  description = "returns a string"
  value       = data.avi_image.this.se_patch_uuid
}

output "status" {
  description = "returns a string"
  value       = data.avi_image.this.status
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_image.this.tenant_ref
}

output "type" {
  description = "returns a string"
  value       = data.avi_image.this.type
}

output "uber_bundle" {
  description = "returns a bool"
  value       = data.avi_image.this.uber_bundle
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_image.this.uuid
}

output "this" {
  value = avi_image.this
}
```

[top](#index)