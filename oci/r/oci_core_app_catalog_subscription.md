# oci_core_app_catalog_subscription

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
module "oci_core_app_catalog_subscription" {
  source = "./modules/oci/r/oci_core_app_catalog_subscription"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # eula_link - (optional) is a type of string
  eula_link = null
  # listing_id - (required) is a type of string
  listing_id = null
  # listing_resource_version - (required) is a type of string
  listing_resource_version = null
  # oracle_terms_of_use_link - (required) is a type of string
  oracle_terms_of_use_link = null
  # signature - (required) is a type of string
  signature = null
  # time_retrieved - (required) is a type of string
  time_retrieved = null

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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "eula_link" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "listing_id" {
  description = "(required)"
  type        = string
}

variable "listing_resource_version" {
  description = "(required)"
  type        = string
}

variable "oracle_terms_of_use_link" {
  description = "(required)"
  type        = string
}

variable "signature" {
  description = "(required)"
  type        = string
}

variable "time_retrieved" {
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
resource "oci_core_app_catalog_subscription" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # eula_link - (optional) is a type of string
  eula_link = var.eula_link
  # listing_id - (required) is a type of string
  listing_id = var.listing_id
  # listing_resource_version - (required) is a type of string
  listing_resource_version = var.listing_resource_version
  # oracle_terms_of_use_link - (required) is a type of string
  oracle_terms_of_use_link = var.oracle_terms_of_use_link
  # signature - (required) is a type of string
  signature = var.signature
  # time_retrieved - (required) is a type of string
  time_retrieved = var.time_retrieved

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
output "display_name" {
  description = "returns a string"
  value       = oci_core_app_catalog_subscription.this.display_name
}

output "id" {
  description = "returns a string"
  value       = oci_core_app_catalog_subscription.this.id
}

output "listing_resource_id" {
  description = "returns a string"
  value       = oci_core_app_catalog_subscription.this.listing_resource_id
}

output "publisher_name" {
  description = "returns a string"
  value       = oci_core_app_catalog_subscription.this.publisher_name
}

output "summary" {
  description = "returns a string"
  value       = oci_core_app_catalog_subscription.this.summary
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_app_catalog_subscription.this.time_created
}

output "this" {
  value = oci_core_app_catalog_subscription.this
}
```

[top](#index)