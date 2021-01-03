# oci_dns_resolver

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_dns_resolver" {
  source = "./modules/oci/d/oci_dns_resolver"

  # resolver_id - (required) is a type of string
  resolver_id = null
  # scope - (required) is a type of string
  scope = null
}
```

[top](#index)

### Variables

```terraform
variable "resolver_id" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_dns_resolver" "this" {
  resolver_id = var.resolver_id
  scope       = var.scope
}
```

[top](#index)

### Outputs

```terraform
output "attached_vcn_id" {
  description = "returns a string"
  value       = data.oci_dns_resolver.this.attached_vcn_id
}

output "attached_views" {
  description = "returns a list of object"
  value       = data.oci_dns_resolver.this.attached_views
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_dns_resolver.this.compartment_id
}

output "default_view_id" {
  description = "returns a string"
  value       = data.oci_dns_resolver.this.default_view_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_dns_resolver.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_dns_resolver.this.display_name
}

output "endpoints" {
  description = "returns a list of object"
  value       = data.oci_dns_resolver.this.endpoints
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_dns_resolver.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_dns_resolver.this.id
}

output "is_protected" {
  description = "returns a bool"
  value       = data.oci_dns_resolver.this.is_protected
}

output "rules" {
  description = "returns a list of object"
  value       = data.oci_dns_resolver.this.rules
}

output "self" {
  description = "returns a string"
  value       = data.oci_dns_resolver.this.self
}

output "state" {
  description = "returns a string"
  value       = data.oci_dns_resolver.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_dns_resolver.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_dns_resolver.this.time_updated
}

output "this" {
  value = oci_dns_resolver.this
}
```

[top](#index)