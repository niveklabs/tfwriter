# avi_poolgroup

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
module "avi_poolgroup" {
  source = "./modules/avi/d/avi_poolgroup"

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
data "avi_poolgroup" "this" {
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
output "cloud_config_cksum" {
  description = "returns a string"
  value       = data.avi_poolgroup.this.cloud_config_cksum
}

output "cloud_ref" {
  description = "returns a string"
  value       = data.avi_poolgroup.this.cloud_ref
}

output "created_by" {
  description = "returns a string"
  value       = data.avi_poolgroup.this.created_by
}

output "deployment_policy_ref" {
  description = "returns a string"
  value       = data.avi_poolgroup.this.deployment_policy_ref
}

output "description" {
  description = "returns a string"
  value       = data.avi_poolgroup.this.description
}

output "fail_action" {
  description = "returns a set of object"
  value       = data.avi_poolgroup.this.fail_action
}

output "id" {
  description = "returns a string"
  value       = data.avi_poolgroup.this.id
}

output "implicit_priority_labels" {
  description = "returns a bool"
  value       = data.avi_poolgroup.this.implicit_priority_labels
}

output "members" {
  description = "returns a list of object"
  value       = data.avi_poolgroup.this.members
}

output "min_servers" {
  description = "returns a number"
  value       = data.avi_poolgroup.this.min_servers
}

output "name" {
  description = "returns a string"
  value       = data.avi_poolgroup.this.name
}

output "priority_labels_ref" {
  description = "returns a string"
  value       = data.avi_poolgroup.this.priority_labels_ref
}

output "service_metadata" {
  description = "returns a string"
  value       = data.avi_poolgroup.this.service_metadata
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_poolgroup.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_poolgroup.this.uuid
}

output "this" {
  value = avi_poolgroup.this
}
```

[top](#index)