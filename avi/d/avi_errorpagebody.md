# avi_errorpagebody

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
module "avi_errorpagebody" {
  source = "./modules/avi/d/avi_errorpagebody"

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
data "avi_errorpagebody" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "error_page_body" {
  description = "returns a string"
  value       = data.avi_errorpagebody.this.error_page_body
}

output "format" {
  description = "returns a string"
  value       = data.avi_errorpagebody.this.format
}

output "id" {
  description = "returns a string"
  value       = data.avi_errorpagebody.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_errorpagebody.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_errorpagebody.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_errorpagebody.this.uuid
}

output "this" {
  value = avi_errorpagebody.this
}
```

[top](#index)