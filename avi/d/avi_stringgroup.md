# avi_stringgroup

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
module "avi_stringgroup" {
  source = "./modules/avi/d/avi_stringgroup"

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
data "avi_stringgroup" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.avi_stringgroup.this.description
}

output "id" {
  description = "returns a string"
  value       = data.avi_stringgroup.this.id
}

output "kv" {
  description = "returns a list of object"
  value       = data.avi_stringgroup.this.kv
}

output "longest_match" {
  description = "returns a bool"
  value       = data.avi_stringgroup.this.longest_match
}

output "name" {
  description = "returns a string"
  value       = data.avi_stringgroup.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_stringgroup.this.tenant_ref
}

output "type" {
  description = "returns a string"
  value       = data.avi_stringgroup.this.type
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_stringgroup.this.uuid
}

output "this" {
  value = avi_stringgroup.this
}
```

[top](#index)