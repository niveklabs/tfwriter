# aci_service_redirect_policy

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
module "aci_service_redirect_policy" {
  source = "./modules/aci/d/aci_service_redirect_policy"

  # annotation - (optional) is a type of string
  annotation = null
  # anycast_enabled - (optional) is a type of string
  anycast_enabled = null
  # description - (optional) is a type of string
  description = null
  # dest_type - (optional) is a type of string
  dest_type = null
  # hashing_algorithm - (optional) is a type of string
  hashing_algorithm = null
  # max_threshold_percent - (optional) is a type of string
  max_threshold_percent = null
  # min_threshold_percent - (optional) is a type of string
  min_threshold_percent = null
  # name - (required) is a type of string
  name = null
  # name_alias - (optional) is a type of string
  name_alias = null
  # program_local_pod_only - (optional) is a type of string
  program_local_pod_only = null
  # resilient_hash_enabled - (optional) is a type of string
  resilient_hash_enabled = null
  # tenant_dn - (required) is a type of string
  tenant_dn = null
  # threshold_down_action - (optional) is a type of string
  threshold_down_action = null
  # threshold_enable - (optional) is a type of string
  threshold_enable = null
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

variable "anycast_enabled" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dest_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hashing_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_threshold_percent" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "min_threshold_percent" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "name_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "program_local_pod_only" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resilient_hash_enabled" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_dn" {
  description = "(required)"
  type        = string
}

variable "threshold_down_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "threshold_enable" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aci_service_redirect_policy" "this" {
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # anycast_enabled - (optional) is a type of string
  anycast_enabled = var.anycast_enabled
  # description - (optional) is a type of string
  description = var.description
  # dest_type - (optional) is a type of string
  dest_type = var.dest_type
  # hashing_algorithm - (optional) is a type of string
  hashing_algorithm = var.hashing_algorithm
  # max_threshold_percent - (optional) is a type of string
  max_threshold_percent = var.max_threshold_percent
  # min_threshold_percent - (optional) is a type of string
  min_threshold_percent = var.min_threshold_percent
  # name - (required) is a type of string
  name = var.name
  # name_alias - (optional) is a type of string
  name_alias = var.name_alias
  # program_local_pod_only - (optional) is a type of string
  program_local_pod_only = var.program_local_pod_only
  # resilient_hash_enabled - (optional) is a type of string
  resilient_hash_enabled = var.resilient_hash_enabled
  # tenant_dn - (required) is a type of string
  tenant_dn = var.tenant_dn
  # threshold_down_action - (optional) is a type of string
  threshold_down_action = var.threshold_down_action
  # threshold_enable - (optional) is a type of string
  threshold_enable = var.threshold_enable
}
```

[top](#index)

### Outputs

```terraform
output "anycast_enabled" {
  description = "returns a string"
  value       = data.aci_service_redirect_policy.this.anycast_enabled
}

output "description" {
  description = "returns a string"
  value       = data.aci_service_redirect_policy.this.description
}

output "dest_type" {
  description = "returns a string"
  value       = data.aci_service_redirect_policy.this.dest_type
}

output "hashing_algorithm" {
  description = "returns a string"
  value       = data.aci_service_redirect_policy.this.hashing_algorithm
}

output "id" {
  description = "returns a string"
  value       = data.aci_service_redirect_policy.this.id
}

output "max_threshold_percent" {
  description = "returns a string"
  value       = data.aci_service_redirect_policy.this.max_threshold_percent
}

output "min_threshold_percent" {
  description = "returns a string"
  value       = data.aci_service_redirect_policy.this.min_threshold_percent
}

output "name_alias" {
  description = "returns a string"
  value       = data.aci_service_redirect_policy.this.name_alias
}

output "program_local_pod_only" {
  description = "returns a string"
  value       = data.aci_service_redirect_policy.this.program_local_pod_only
}

output "resilient_hash_enabled" {
  description = "returns a string"
  value       = data.aci_service_redirect_policy.this.resilient_hash_enabled
}

output "threshold_down_action" {
  description = "returns a string"
  value       = data.aci_service_redirect_policy.this.threshold_down_action
}

output "threshold_enable" {
  description = "returns a string"
  value       = data.aci_service_redirect_policy.this.threshold_enable
}

output "this" {
  value = aci_service_redirect_policy.this
}
```

[top](#index)