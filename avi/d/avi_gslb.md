# avi_gslb

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
module "avi_gslb" {
  source = "./modules/avi/d/avi_gslb"

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
data "avi_gslb" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "async_interval" {
  description = "returns a number"
  value       = data.avi_gslb.this.async_interval
}

output "clear_on_max_retries" {
  description = "returns a number"
  value       = data.avi_gslb.this.clear_on_max_retries
}

output "client_ip_addr_group" {
  description = "returns a set of object"
  value       = data.avi_gslb.this.client_ip_addr_group
}

output "description" {
  description = "returns a string"
  value       = data.avi_gslb.this.description
}

output "dns_configs" {
  description = "returns a list of object"
  value       = data.avi_gslb.this.dns_configs
}

output "error_resync_interval" {
  description = "returns a number"
  value       = data.avi_gslb.this.error_resync_interval
}

output "id" {
  description = "returns a string"
  value       = data.avi_gslb.this.id
}

output "is_federated" {
  description = "returns a bool"
  value       = data.avi_gslb.this.is_federated
}

output "leader_cluster_uuid" {
  description = "returns a string"
  value       = data.avi_gslb.this.leader_cluster_uuid
}

output "maintenance_mode" {
  description = "returns a bool"
  value       = data.avi_gslb.this.maintenance_mode
}

output "name" {
  description = "returns a string"
  value       = data.avi_gslb.this.name
}

output "send_interval" {
  description = "returns a number"
  value       = data.avi_gslb.this.send_interval
}

output "send_interval_prior_to_maintenance_mode" {
  description = "returns a number"
  value       = data.avi_gslb.this.send_interval_prior_to_maintenance_mode
}

output "sites" {
  description = "returns a list of object"
  value       = data.avi_gslb.this.sites
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_gslb.this.tenant_ref
}

output "third_party_sites" {
  description = "returns a list of object"
  value       = data.avi_gslb.this.third_party_sites
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_gslb.this.uuid
}

output "view_id" {
  description = "returns a number"
  value       = data.avi_gslb.this.view_id
}

output "this" {
  value = avi_gslb.this
}
```

[top](#index)