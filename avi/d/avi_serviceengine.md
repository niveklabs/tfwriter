# avi_serviceengine

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
module "avi_serviceengine" {
  source = "./modules/avi/d/avi_serviceengine"

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
data "avi_serviceengine" "this" {
  # cloud_ref - (optional) is a type of string
  cloud_ref = var.cloud_ref
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
output "availability_zone" {
  description = "returns a string"
  value       = data.avi_serviceengine.this.availability_zone
}

output "cloud_ref" {
  description = "returns a string"
  value       = data.avi_serviceengine.this.cloud_ref
}

output "container_mode" {
  description = "returns a bool"
  value       = data.avi_serviceengine.this.container_mode
}

output "container_type" {
  description = "returns a string"
  value       = data.avi_serviceengine.this.container_type
}

output "controller_created" {
  description = "returns a bool"
  value       = data.avi_serviceengine.this.controller_created
}

output "controller_ip" {
  description = "returns a string"
  value       = data.avi_serviceengine.this.controller_ip
}

output "data_vnics" {
  description = "returns a list of object"
  value       = data.avi_serviceengine.this.data_vnics
}

output "enable_state" {
  description = "returns a string"
  value       = data.avi_serviceengine.this.enable_state
}

output "flavor" {
  description = "returns a string"
  value       = data.avi_serviceengine.this.flavor
}

output "host_ref" {
  description = "returns a string"
  value       = data.avi_serviceengine.this.host_ref
}

output "hypervisor" {
  description = "returns a string"
  value       = data.avi_serviceengine.this.hypervisor
}

output "id" {
  description = "returns a string"
  value       = data.avi_serviceengine.this.id
}

output "mgmt_vnic" {
  description = "returns a set of object"
  value       = data.avi_serviceengine.this.mgmt_vnic
}

output "name" {
  description = "returns a string"
  value       = data.avi_serviceengine.this.name
}

output "resources" {
  description = "returns a set of object"
  value       = data.avi_serviceengine.this.resources
}

output "se_group_ref" {
  description = "returns a string"
  value       = data.avi_serviceengine.this.se_group_ref
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_serviceengine.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_serviceengine.this.uuid
}

output "this" {
  value = avi_serviceengine.this
}
```

[top](#index)