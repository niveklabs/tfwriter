# oci_marketplace_listing_package_agreements

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
module "oci_marketplace_listing_package_agreements" {
  source = "./modules/oci/d/oci_marketplace_listing_package_agreements"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # listing_id - (required) is a type of string
  listing_id = null
  # package_version - (required) is a type of string
  package_version = null

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
variable "compartment_id" {
  description = "(optional)"
  type        = string
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
data "oci_marketplace_listing_package_agreements" "this" {
  # compartment_id - (optional) is a type of string
  compartment_id = var.compartment_id
  # listing_id - (required) is a type of string
  listing_id = var.listing_id
  # package_version - (required) is a type of string
  package_version = var.package_version

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # regex - (optional) is a type of bool
      regex = filter.value["regex"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "agreements" {
  description = "returns a list of object"
  value       = data.oci_marketplace_listing_package_agreements.this.agreements
}

output "id" {
  description = "returns a string"
  value       = data.oci_marketplace_listing_package_agreements.this.id
}

output "this" {
  value = oci_marketplace_listing_package_agreements.this
}
```

[top](#index)