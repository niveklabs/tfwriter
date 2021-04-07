# avi_tenant

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
module "avi_tenant" {
  source = "./modules/avi/d/avi_tenant"

  # name - (optional) is a type of string
  name = null
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

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_tenant" "this" {
  # name - (optional) is a type of string
  name = var.name
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "config_settings" {
  description = "returns a set of object"
  value       = data.avi_tenant.this.config_settings
}

output "created_by" {
  description = "returns a string"
  value       = data.avi_tenant.this.created_by
}

output "description" {
  description = "returns a string"
  value       = data.avi_tenant.this.description
}

output "id" {
  description = "returns a string"
  value       = data.avi_tenant.this.id
}

output "local" {
  description = "returns a bool"
  value       = data.avi_tenant.this.local
}

output "name" {
  description = "returns a string"
  value       = data.avi_tenant.this.name
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_tenant.this.uuid
}

output "this" {
  value = avi_tenant.this
}
```

[top](#index)