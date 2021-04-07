# avi_ipaddrgroup

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
module "avi_ipaddrgroup" {
  source = "./modules/avi/d/avi_ipaddrgroup"

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
data "avi_ipaddrgroup" "this" {
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
output "addrs" {
  description = "returns a list of object"
  value       = data.avi_ipaddrgroup.this.addrs
}

output "apic_epg_name" {
  description = "returns a string"
  value       = data.avi_ipaddrgroup.this.apic_epg_name
}

output "country_codes" {
  description = "returns a list of string"
  value       = data.avi_ipaddrgroup.this.country_codes
}

output "description" {
  description = "returns a string"
  value       = data.avi_ipaddrgroup.this.description
}

output "id" {
  description = "returns a string"
  value       = data.avi_ipaddrgroup.this.id
}

output "ip_ports" {
  description = "returns a list of object"
  value       = data.avi_ipaddrgroup.this.ip_ports
}

output "marathon_app_name" {
  description = "returns a string"
  value       = data.avi_ipaddrgroup.this.marathon_app_name
}

output "marathon_service_port" {
  description = "returns a number"
  value       = data.avi_ipaddrgroup.this.marathon_service_port
}

output "name" {
  description = "returns a string"
  value       = data.avi_ipaddrgroup.this.name
}

output "prefixes" {
  description = "returns a list of object"
  value       = data.avi_ipaddrgroup.this.prefixes
}

output "ranges" {
  description = "returns a list of object"
  value       = data.avi_ipaddrgroup.this.ranges
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_ipaddrgroup.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_ipaddrgroup.this.uuid
}

output "this" {
  value = avi_ipaddrgroup.this
}
```

[top](#index)