# avi_controllersite

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
module "avi_controllersite" {
  source = "./modules/avi/d/avi_controllersite"

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
data "avi_controllersite" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = data.avi_controllersite.this.address
}

output "id" {
  description = "returns a string"
  value       = data.avi_controllersite.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_controllersite.this.name
}

output "port" {
  description = "returns a number"
  value       = data.avi_controllersite.this.port
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_controllersite.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_controllersite.this.uuid
}

output "this" {
  value = avi_controllersite.this
}
```

[top](#index)