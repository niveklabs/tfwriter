# oci_marketplace_listing_package_agreement

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_marketplace_listing_package_agreement" {
  source = "./modules/oci/r/oci_marketplace_listing_package_agreement"

  # agreement_id - (required) is a type of string
  agreement_id = null
  # listing_id - (required) is a type of string
  listing_id = null
  # package_version - (required) is a type of string
  package_version = null
}
```

[top](#index)

### Variables

```terraform
variable "agreement_id" {
  description = "(required)"
  type        = string
}

variable "listing_id" {
  description = "(required)"
  type        = string
}

variable "package_version" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "oci_marketplace_listing_package_agreement" "this" {
  agreement_id    = var.agreement_id
  listing_id      = var.listing_id
  package_version = var.package_version
}
```

[top](#index)

### Outputs

```terraform
output "author" {
  description = "returns a string"
  value       = oci_marketplace_listing_package_agreement.this.author
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_marketplace_listing_package_agreement.this.compartment_id
}

output "content_url" {
  description = "returns a string"
  value       = oci_marketplace_listing_package_agreement.this.content_url
}

output "id" {
  description = "returns a string"
  value       = oci_marketplace_listing_package_agreement.this.id
}

output "prompt" {
  description = "returns a string"
  value       = oci_marketplace_listing_package_agreement.this.prompt
}

output "signature" {
  description = "returns a string"
  value       = oci_marketplace_listing_package_agreement.this.signature
}

output "this" {
  value = oci_marketplace_listing_package_agreement.this
}
```

[top](#index)