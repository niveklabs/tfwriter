# avi_gslbservice

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
module "avi_gslbservice" {
  source = "./modules/avi/d/avi_gslbservice"

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
data "avi_gslbservice" "this" {
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
output "application_persistence_profile_ref" {
  description = "returns a string"
  value       = data.avi_gslbservice.this.application_persistence_profile_ref
}

output "controller_health_status_enabled" {
  description = "returns a bool"
  value       = data.avi_gslbservice.this.controller_health_status_enabled
}

output "created_by" {
  description = "returns a string"
  value       = data.avi_gslbservice.this.created_by
}

output "description" {
  description = "returns a string"
  value       = data.avi_gslbservice.this.description
}

output "domain_names" {
  description = "returns a list of string"
  value       = data.avi_gslbservice.this.domain_names
}

output "down_response" {
  description = "returns a set of object"
  value       = data.avi_gslbservice.this.down_response
}

output "enabled" {
  description = "returns a bool"
  value       = data.avi_gslbservice.this.enabled
}

output "groups" {
  description = "returns a list of object"
  value       = data.avi_gslbservice.this.groups
}

output "health_monitor_refs" {
  description = "returns a list of string"
  value       = data.avi_gslbservice.this.health_monitor_refs
}

output "health_monitor_scope" {
  description = "returns a string"
  value       = data.avi_gslbservice.this.health_monitor_scope
}

output "hm_off" {
  description = "returns a bool"
  value       = data.avi_gslbservice.this.hm_off
}

output "id" {
  description = "returns a string"
  value       = data.avi_gslbservice.this.id
}

output "is_federated" {
  description = "returns a bool"
  value       = data.avi_gslbservice.this.is_federated
}

output "min_members" {
  description = "returns a number"
  value       = data.avi_gslbservice.this.min_members
}

output "name" {
  description = "returns a string"
  value       = data.avi_gslbservice.this.name
}

output "num_dns_ip" {
  description = "returns a number"
  value       = data.avi_gslbservice.this.num_dns_ip
}

output "pool_algorithm" {
  description = "returns a string"
  value       = data.avi_gslbservice.this.pool_algorithm
}

output "resolve_cname" {
  description = "returns a bool"
  value       = data.avi_gslbservice.this.resolve_cname
}

output "site_persistence_enabled" {
  description = "returns a bool"
  value       = data.avi_gslbservice.this.site_persistence_enabled
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_gslbservice.this.tenant_ref
}

output "ttl" {
  description = "returns a number"
  value       = data.avi_gslbservice.this.ttl
}

output "use_edns_client_subnet" {
  description = "returns a bool"
  value       = data.avi_gslbservice.this.use_edns_client_subnet
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_gslbservice.this.uuid
}

output "wildcard_match" {
  description = "returns a bool"
  value       = data.avi_gslbservice.this.wildcard_match
}

output "this" {
  value = avi_gslbservice.this
}
```

[top](#index)