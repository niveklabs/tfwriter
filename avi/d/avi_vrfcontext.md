# avi_vrfcontext

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
module "avi_vrfcontext" {
  source = "./modules/avi/d/avi_vrfcontext"

  # cloud_ref - (optional) is a type of string
  cloud_ref = null
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
variable "cloud_ref" {
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

### Datasource

```terraform
data "avi_vrfcontext" "this" {
  cloud_ref  = var.cloud_ref
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "bgp_profile" {
  description = "returns a set of object"
  value       = data.avi_vrfcontext.this.bgp_profile
}

output "cloud_ref" {
  description = "returns a string"
  value       = data.avi_vrfcontext.this.cloud_ref
}

output "debugvrfcontext" {
  description = "returns a set of object"
  value       = data.avi_vrfcontext.this.debugvrfcontext
}

output "description" {
  description = "returns a string"
  value       = data.avi_vrfcontext.this.description
}

output "gateway_mon" {
  description = "returns a list of object"
  value       = data.avi_vrfcontext.this.gateway_mon
}

output "id" {
  description = "returns a string"
  value       = data.avi_vrfcontext.this.id
}

output "internal_gateway_monitor" {
  description = "returns a set of object"
  value       = data.avi_vrfcontext.this.internal_gateway_monitor
}

output "labels" {
  description = "returns a list of object"
  value       = data.avi_vrfcontext.this.labels
}

output "name" {
  description = "returns a string"
  value       = data.avi_vrfcontext.this.name
}

output "static_routes" {
  description = "returns a list of object"
  value       = data.avi_vrfcontext.this.static_routes
}

output "system_default" {
  description = "returns a bool"
  value       = data.avi_vrfcontext.this.system_default
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_vrfcontext.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_vrfcontext.this.uuid
}

output "this" {
  value = avi_vrfcontext.this
}
```

[top](#index)