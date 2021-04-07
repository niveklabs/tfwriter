# avi_controllersite

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
module "avi_controllersite" {
  source = "./modules/avi/r/avi_controllersite"

  # address - (optional) is a type of string
  address = null
  # name - (optional) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
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
resource "avi_controllersite" "this" {
  # address - (optional) is a type of string
  address = var.address
  # name - (optional) is a type of string
  name = var.name
  # port - (optional) is a type of number
  port = var.port
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = avi_controllersite.this.address
}

output "id" {
  description = "returns a string"
  value       = avi_controllersite.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_controllersite.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_controllersite.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_controllersite.this.uuid
}

output "this" {
  value = avi_controllersite.this
}
```

[top](#index)