# oci_marketplace_listings

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
module "oci_marketplace_listings" {
  source = "./modules/oci/d/oci_marketplace_listings"

  # category - (optional) is a type of list of string
  category = []
  # compartment_id - (optional) is a type of string
  compartment_id = null
  # is_featured - (optional) is a type of bool
  is_featured = null
  # listing_id - (optional) is a type of string
  listing_id = null
  # listing_types - (optional) is a type of list of string
  listing_types = []
  # name - (optional) is a type of list of string
  name = []
  # operating_systems - (optional) is a type of list of string
  operating_systems = []
  # package_type - (optional) is a type of string
  package_type = null
  # pricing - (optional) is a type of list of string
  pricing = []
  # publisher_id - (optional) is a type of string
  publisher_id = null

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
variable "category" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_featured" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "listing_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "listing_types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "operating_systems" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "package_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pricing" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "publisher_id" {
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
data "oci_marketplace_listings" "this" {
  category          = var.category
  compartment_id    = var.compartment_id
  is_featured       = var.is_featured
  listing_id        = var.listing_id
  listing_types     = var.listing_types
  name              = var.name
  operating_systems = var.operating_systems
  package_type      = var.package_type
  pricing           = var.pricing
  publisher_id      = var.publisher_id

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
output "id" {
  description = "returns a string"
  value       = data.oci_marketplace_listings.this.id
}

output "listings" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listings.this.listings
}

output "this" {
  value = oci_marketplace_listings.this
}
```

[top](#index)