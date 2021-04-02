# oci_datacatalog_catalog_private_endpoint

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_datacatalog_catalog_private_endpoint" {
  source = "./modules/oci/r/oci_datacatalog_catalog_private_endpoint"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # dns_zones - (required) is a type of list of string
  dns_zones = []
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # subnet_id - (required) is a type of string
  subnet_id = null

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

variable "dns_zones" {
  description = "(required)"
  type        = list(string)
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "subnet_id" {
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
resource "oci_datacatalog_catalog_private_endpoint" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  dns_zones      = var.dns_zones
  freeform_tags  = var.freeform_tags
  subnet_id      = var.subnet_id

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
output "attached_catalogs" {
  description = "returns a list of string"
  value       = oci_datacatalog_catalog_private_endpoint.this.attached_catalogs
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_datacatalog_catalog_private_endpoint.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_datacatalog_catalog_private_endpoint.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_datacatalog_catalog_private_endpoint.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_datacatalog_catalog_private_endpoint.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_datacatalog_catalog_private_endpoint.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = oci_datacatalog_catalog_private_endpoint.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_datacatalog_catalog_private_endpoint.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_datacatalog_catalog_private_endpoint.this.time_updated
}

output "this" {
  value = oci_datacatalog_catalog_private_endpoint.this
}
```

[top](#index)