# avi_networkservice

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
module "avi_networkservice" {
  source = "./modules/avi/d/avi_networkservice"

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
data "avi_networkservice" "this" {
  cloud_ref  = var.cloud_ref
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "cloud_ref" {
  description = "returns a string"
  value       = data.avi_networkservice.this.cloud_ref
}

output "id" {
  description = "returns a string"
  value       = data.avi_networkservice.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_networkservice.this.name
}

output "routing_service" {
  description = "returns a set of object"
  value       = data.avi_networkservice.this.routing_service
}

output "se_group_ref" {
  description = "returns a string"
  value       = data.avi_networkservice.this.se_group_ref
}

output "service_type" {
  description = "returns a string"
  value       = data.avi_networkservice.this.service_type
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_networkservice.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_networkservice.this.uuid
}

output "vrf_ref" {
  description = "returns a string"
  value       = data.avi_networkservice.this.vrf_ref
}

output "this" {
  value = avi_networkservice.this
}
```

[top](#index)