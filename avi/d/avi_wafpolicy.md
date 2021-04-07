# avi_wafpolicy

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
module "avi_wafpolicy" {
  source = "./modules/avi/d/avi_wafpolicy"

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
data "avi_wafpolicy" "this" {
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
output "allow_mode_delegation" {
  description = "returns a bool"
  value       = data.avi_wafpolicy.this.allow_mode_delegation
}

output "created_by" {
  description = "returns a string"
  value       = data.avi_wafpolicy.this.created_by
}

output "crs_groups" {
  description = "returns a list of object"
  value       = data.avi_wafpolicy.this.crs_groups
}

output "description" {
  description = "returns a string"
  value       = data.avi_wafpolicy.this.description
}

output "enable_app_learning" {
  description = "returns a bool"
  value       = data.avi_wafpolicy.this.enable_app_learning
}

output "failure_mode" {
  description = "returns a string"
  value       = data.avi_wafpolicy.this.failure_mode
}

output "id" {
  description = "returns a string"
  value       = data.avi_wafpolicy.this.id
}

output "mode" {
  description = "returns a string"
  value       = data.avi_wafpolicy.this.mode
}

output "name" {
  description = "returns a string"
  value       = data.avi_wafpolicy.this.name
}

output "paranoia_level" {
  description = "returns a string"
  value       = data.avi_wafpolicy.this.paranoia_level
}

output "positive_security_model" {
  description = "returns a set of object"
  value       = data.avi_wafpolicy.this.positive_security_model
}

output "post_crs_groups" {
  description = "returns a list of object"
  value       = data.avi_wafpolicy.this.post_crs_groups
}

output "pre_crs_groups" {
  description = "returns a list of object"
  value       = data.avi_wafpolicy.this.pre_crs_groups
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_wafpolicy.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_wafpolicy.this.uuid
}

output "waf_crs_ref" {
  description = "returns a string"
  value       = data.avi_wafpolicy.this.waf_crs_ref
}

output "waf_profile_ref" {
  description = "returns a string"
  value       = data.avi_wafpolicy.this.waf_profile_ref
}

output "whitelist" {
  description = "returns a set of object"
  value       = data.avi_wafpolicy.this.whitelist
}

output "this" {
  value = avi_wafpolicy.this
}
```

[top](#index)