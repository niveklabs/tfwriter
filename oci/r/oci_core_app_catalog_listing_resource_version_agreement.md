# oci_core_app_catalog_listing_resource_version_agreement

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
module "oci_core_app_catalog_listing_resource_version_agreement" {
  source = "./modules/oci/r/oci_core_app_catalog_listing_resource_version_agreement"

  # listing_id - (required) is a type of string
  listing_id = null
  # listing_resource_version - (required) is a type of string
  listing_resource_version = null

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
variable "listing_id" {
  description = "(required)"
  type        = string
}

variable "listing_resource_version" {
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
resource "oci_core_app_catalog_listing_resource_version_agreement" "this" {
  # listing_id - (required) is a type of string
  listing_id = var.listing_id
  # listing_resource_version - (required) is a type of string
  listing_resource_version = var.listing_resource_version

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
output "eula_link" {
  description = "returns a string"
  value       = oci_core_app_catalog_listing_resource_version_agreement.this.eula_link
}

output "id" {
  description = "returns a string"
  value       = oci_core_app_catalog_listing_resource_version_agreement.this.id
}

output "oracle_terms_of_use_link" {
  description = "returns a string"
  value       = oci_core_app_catalog_listing_resource_version_agreement.this.oracle_terms_of_use_link
}

output "signature" {
  description = "returns a string"
  value       = oci_core_app_catalog_listing_resource_version_agreement.this.signature
}

output "time_retrieved" {
  description = "returns a string"
  value       = oci_core_app_catalog_listing_resource_version_agreement.this.time_retrieved
}

output "this" {
  value = oci_core_app_catalog_listing_resource_version_agreement.this
}
```

[top](#index)