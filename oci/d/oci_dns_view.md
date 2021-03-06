# oci_dns_view

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_dns_view" {
  source = "./modules/oci/d/oci_dns_view"

  # scope - (required) is a type of string
  scope = null
  # view_id - (required) is a type of string
  view_id = null
}
```

[top](#index)

### Variables

```terraform
variable "scope" {
  description = "(required)"
  type        = string
}

variable "view_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_dns_view" "this" {
  # scope - (required) is a type of string
  scope = var.scope
  # view_id - (required) is a type of string
  view_id = var.view_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_dns_view.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_dns_view.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_dns_view.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_dns_view.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_dns_view.this.id
}

output "is_protected" {
  description = "returns a bool"
  value       = data.oci_dns_view.this.is_protected
}

output "self" {
  description = "returns a string"
  value       = data.oci_dns_view.this.self
}

output "state" {
  description = "returns a string"
  value       = data.oci_dns_view.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_dns_view.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_dns_view.this.time_updated
}

output "this" {
  value = oci_dns_view.this
}
```

[top](#index)