# oci_identity_tenancy

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
module "oci_identity_tenancy" {
  source = "./modules/oci/d/oci_identity_tenancy"

  # tenancy_id - (required) is a type of string
  tenancy_id = null
}
```

[top](#index)

### Variables

```terraform
variable "tenancy_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_identity_tenancy" "this" {
  tenancy_id = var.tenancy_id
}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_identity_tenancy.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_identity_tenancy.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_identity_tenancy.this.freeform_tags
}

output "home_region_key" {
  description = "returns a string"
  value       = data.oci_identity_tenancy.this.home_region_key
}

output "id" {
  description = "returns a string"
  value       = data.oci_identity_tenancy.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_identity_tenancy.this.name
}

output "upi_idcs_compatibility_layer_endpoint" {
  description = "returns a string"
  value       = data.oci_identity_tenancy.this.upi_idcs_compatibility_layer_endpoint
}

output "this" {
  value = oci_identity_tenancy.this
}
```

[top](#index)