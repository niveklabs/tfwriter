# avi_wafcrs

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
module "avi_wafcrs" {
  source = "./modules/avi/d/avi_wafcrs"

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
data "avi_wafcrs" "this" {
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
output "description" {
  description = "returns a string"
  value       = data.avi_wafcrs.this.description
}

output "groups" {
  description = "returns a list of object"
  value       = data.avi_wafcrs.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.avi_wafcrs.this.id
}

output "integrity" {
  description = "returns a string"
  value       = data.avi_wafcrs.this.integrity
}

output "name" {
  description = "returns a string"
  value       = data.avi_wafcrs.this.name
}

output "release_date" {
  description = "returns a string"
  value       = data.avi_wafcrs.this.release_date
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_wafcrs.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_wafcrs.this.uuid
}

output "version" {
  description = "returns a string"
  value       = data.avi_wafcrs.this.version
}

output "this" {
  value = avi_wafcrs.this
}
```

[top](#index)