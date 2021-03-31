# avi_errorpagebody

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
module "avi_errorpagebody" {
  source = "./modules/avi/r/avi_errorpagebody"

  # error_page_body - (optional) is a type of string
  error_page_body = null
  # format - (optional) is a type of string
  format = null
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
variable "error_page_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "format" {
  description = "(optional)"
  type        = string
  default     = null
}

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

### Resource

```terraform
resource "avi_errorpagebody" "this" {
  error_page_body = var.error_page_body
  format          = var.format
  name            = var.name
  tenant_ref      = var.tenant_ref
  uuid            = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "error_page_body" {
  description = "returns a string"
  value       = avi_errorpagebody.this.error_page_body
}

output "id" {
  description = "returns a string"
  value       = avi_errorpagebody.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_errorpagebody.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_errorpagebody.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_errorpagebody.this.uuid
}

output "this" {
  value = avi_errorpagebody.this
}
```

[top](#index)