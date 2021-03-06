# avi_controllerportalregistration

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
module "avi_controllerportalregistration" {
  source = "./modules/avi/d/avi_controllerportalregistration"

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
data "avi_controllerportalregistration" "this" {
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
output "asset" {
  description = "returns a set of object"
  value       = data.avi_controllerportalregistration.this.asset
}

output "id" {
  description = "returns a string"
  value       = data.avi_controllerportalregistration.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_controllerportalregistration.this.name
}

output "portal_auth" {
  description = "returns a set of object"
  value       = data.avi_controllerportalregistration.this.portal_auth
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_controllerportalregistration.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_controllerportalregistration.this.uuid
}

output "this" {
  value = avi_controllerportalregistration.this
}
```

[top](#index)