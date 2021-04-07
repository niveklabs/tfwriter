# oci_marketplace_accepted_agreement

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_marketplace_accepted_agreement" {
  source = "./modules/oci/r/oci_marketplace_accepted_agreement"

  # agreement_id - (required) is a type of string
  agreement_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # listing_id - (required) is a type of string
  listing_id = null
  # package_version - (required) is a type of string
  package_version = null
  # signature - (required) is a type of string
  signature = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "agreement_id" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "listing_id" {
  description = "(required)"
  type        = string
}

variable "package_version" {
  description = "(required)"
  type        = string
}

variable "signature" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_marketplace_accepted_agreement" "this" {
  # agreement_id - (required) is a type of string
  agreement_id = var.agreement_id
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # listing_id - (required) is a type of string
  listing_id = var.listing_id
  # package_version - (required) is a type of string
  package_version = var.package_version
  # signature - (required) is a type of string
  signature = var.signature

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_marketplace_accepted_agreement.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_marketplace_accepted_agreement.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_marketplace_accepted_agreement.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_marketplace_accepted_agreement.this.id
}

output "time_accepted" {
  description = "returns a string"
  value       = oci_marketplace_accepted_agreement.this.time_accepted
}

output "this" {
  value = oci_marketplace_accepted_agreement.this
}
```

[top](#index)