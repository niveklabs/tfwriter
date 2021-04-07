# oci_marketplace_accepted_agreement

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
module "oci_marketplace_accepted_agreement" {
  source = "./modules/oci/d/oci_marketplace_accepted_agreement"

  # accepted_agreement_id - (required) is a type of string
  accepted_agreement_id = null
}
```

[top](#index)

### Variables

```terraform
variable "accepted_agreement_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_marketplace_accepted_agreement" "this" {
  accepted_agreement_id = var.accepted_agreement_id
}
```

[top](#index)

### Outputs

```terraform
output "agreement_id" {
  description = "returns a string"
  value       = data.oci_marketplace_accepted_agreement.this.agreement_id
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_marketplace_accepted_agreement.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_marketplace_accepted_agreement.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_marketplace_accepted_agreement.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_marketplace_accepted_agreement.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_marketplace_accepted_agreement.this.id
}

output "listing_id" {
  description = "returns a string"
  value       = data.oci_marketplace_accepted_agreement.this.listing_id
}

output "package_version" {
  description = "returns a string"
  value       = data.oci_marketplace_accepted_agreement.this.package_version
}

output "signature" {
  description = "returns a string"
  value       = data.oci_marketplace_accepted_agreement.this.signature
}

output "time_accepted" {
  description = "returns a string"
  value       = data.oci_marketplace_accepted_agreement.this.time_accepted
}

output "this" {
  value = oci_marketplace_accepted_agreement.this
}
```

[top](#index)