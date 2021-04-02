# oci_core_app_catalog_listing_resource_versions

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_app_catalog_listing_resource_versions" {
  source = "./modules/oci/d/oci_core_app_catalog_listing_resource_versions"

  # listing_id - (required) is a type of string
  listing_id = null

  filter = [{
    name   = null
    regex  = null
    values = []
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

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_app_catalog_listing_resource_versions" "this" {
  listing_id = var.listing_id

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "app_catalog_listing_resource_versions" {
  description = "returns a list of object"
  value       = data.oci_core_app_catalog_listing_resource_versions.this.app_catalog_listing_resource_versions
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listing_resource_versions.this.id
}

output "this" {
  value = oci_core_app_catalog_listing_resource_versions.this
}
```

[top](#index)