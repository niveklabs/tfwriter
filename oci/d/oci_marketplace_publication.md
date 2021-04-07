# oci_marketplace_publication

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
module "oci_marketplace_publication" {
  source = "./modules/oci/d/oci_marketplace_publication"

  # publication_id - (required) is a type of string
  publication_id = null
}
```

[top](#index)

### Variables

```terraform
variable "publication_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_marketplace_publication" "this" {
  publication_id = var.publication_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_marketplace_publication.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_marketplace_publication.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_marketplace_publication.this.freeform_tags
}

output "icon" {
  description = "returns a list of object"
  value       = data.oci_marketplace_publication.this.icon
}

output "id" {
  description = "returns a string"
  value       = data.oci_marketplace_publication.this.id
}

output "is_agreement_acknowledged" {
  description = "returns a bool"
  value       = data.oci_marketplace_publication.this.is_agreement_acknowledged
}

output "listing_type" {
  description = "returns a string"
  value       = data.oci_marketplace_publication.this.listing_type
}

output "long_description" {
  description = "returns a string"
  value       = data.oci_marketplace_publication.this.long_description
}

output "name" {
  description = "returns a string"
  value       = data.oci_marketplace_publication.this.name
}

output "package_details" {
  description = "returns a list of object"
  value       = data.oci_marketplace_publication.this.package_details
}

output "package_type" {
  description = "returns a string"
  value       = data.oci_marketplace_publication.this.package_type
}

output "short_description" {
  description = "returns a string"
  value       = data.oci_marketplace_publication.this.short_description
}

output "state" {
  description = "returns a string"
  value       = data.oci_marketplace_publication.this.state
}

output "support_contacts" {
  description = "returns a list of object"
  value       = data.oci_marketplace_publication.this.support_contacts
}

output "supported_operating_systems" {
  description = "returns a list of object"
  value       = data.oci_marketplace_publication.this.supported_operating_systems
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_marketplace_publication.this.time_created
}

output "this" {
  value = oci_marketplace_publication.this
}
```

[top](#index)