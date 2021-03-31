# aci_fabric_node_member

[back](../aci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aci = ">= 0.5.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aci_fabric_node_member" {
  source = "./modules/aci/d/aci_fabric_node_member"

  # annotation - (optional) is a type of string
  annotation = null
  # description - (optional) is a type of string
  description = null
  # ext_pool_id - (optional) is a type of string
  ext_pool_id = null
  # fabric_id - (optional) is a type of string
  fabric_id = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # node_id - (optional) is a type of string
  node_id = null
  # node_type - (optional) is a type of string
  node_type = null
  # pod_id - (optional) is a type of string
  pod_id = null
  # role - (optional) is a type of string
  role = null
  # serial - (required) is a type of string
  serial = null
}
```

[top](#index)

### Variables

```terraform
variable "annotation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ext_pool_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fabric_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pod_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "serial" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aci_fabric_node_member" "this" {
  annotation  = var.annotation
  description = var.description
  ext_pool_id = var.ext_pool_id
  fabric_id   = var.fabric_id
  name_alias  = var.name_alias
  node_id     = var.node_id
  node_type   = var.node_type
  pod_id      = var.pod_id
  role        = var.role
  serial      = var.serial
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.aci_fabric_node_member.this.description
}

output "ext_pool_id" {
  description = "returns a string"
  value       = data.aci_fabric_node_member.this.ext_pool_id
}

output "fabric_id" {
  description = "returns a string"
  value       = data.aci_fabric_node_member.this.fabric_id
}

output "id" {
  description = "returns a string"
  value       = data.aci_fabric_node_member.this.id
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_fabric_node_member.this.name_alias
}

output "node_id" {
  description = "returns a string"
  value       = data.aci_fabric_node_member.this.node_id
}

output "node_type" {
  description = "returns a string"
  value       = data.aci_fabric_node_member.this.node_type
}

output "pod_id" {
  description = "returns a string"
  value       = data.aci_fabric_node_member.this.pod_id
}

output "role" {
  description = "returns a string"
  value       = data.aci_fabric_node_member.this.role
}

output "this" {
  value = aci_fabric_node_member.this
}
```

[top](#index)