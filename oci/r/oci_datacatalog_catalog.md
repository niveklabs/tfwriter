# oci_datacatalog_catalog

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_datacatalog_catalog" {
  source = "./modules/oci/r/oci_datacatalog_catalog"

  # attached_catalog_private_endpoints - (optional) is a type of set of string
  attached_catalog_private_endpoints = []
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}

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
variable "attached_catalog_private_endpoints" {
  description = "(optional)"
  type        = set(string)
  default     = null
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
resource "oci_datacatalog_catalog" "this" {
  attached_catalog_private_endpoints = var.attached_catalog_private_endpoints
  compartment_id                     = var.compartment_id
  defined_tags                       = var.defined_tags
  display_name                       = var.display_name
  freeform_tags                      = var.freeform_tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "attached_catalog_private_endpoints" {
  description = "returns a set of string"
  value       = oci_datacatalog_catalog.this.attached_catalog_private_endpoints
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_datacatalog_catalog.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_datacatalog_catalog.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_datacatalog_catalog.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_datacatalog_catalog.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_datacatalog_catalog.this.lifecycle_details
}

output "number_of_objects" {
  description = "returns a number"
  value       = oci_datacatalog_catalog.this.number_of_objects
}

output "service_api_url" {
  description = "returns a string"
  value       = oci_datacatalog_catalog.this.service_api_url
}

output "service_console_url" {
  description = "returns a string"
  value       = oci_datacatalog_catalog.this.service_console_url
}

output "state" {
  description = "returns a string"
  value       = oci_datacatalog_catalog.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_datacatalog_catalog.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_datacatalog_catalog.this.time_updated
}

output "this" {
  value = oci_datacatalog_catalog.this
}
```

[top](#index)