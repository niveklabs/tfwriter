# oci_core_app_catalog_listings

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
module "oci_core_app_catalog_listings" {
  source = "./modules/oci/d/oci_core_app_catalog_listings"

  # display_name - (optional) is a type of string
  display_name = null
  # publisher_name - (optional) is a type of string
  publisher_name = null
  # publisher_type - (optional) is a type of string
  publisher_type = null

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
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "publisher_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "publisher_type" {
  description = "(optional)"
  type        = string
  default     = null
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
data "oci_core_app_catalog_listings" "this" {
  display_name   = var.display_name
  publisher_name = var.publisher_name
  publisher_type = var.publisher_type

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
output "app_catalog_listings" {
  description = "returns a list of object"
  value       = data.oci_core_app_catalog_listings.this.app_catalog_listings
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_listings.this.id
}

output "this" {
  value = oci_core_app_catalog_listings.this
}
```

[top](#index)