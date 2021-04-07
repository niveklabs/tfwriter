# oci_core_app_catalog_subscriptions

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
module "oci_core_app_catalog_subscriptions" {
  source = "./modules/oci/d/oci_core_app_catalog_subscriptions"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # listing_id - (optional) is a type of string
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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "listing_id" {
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
data "oci_core_app_catalog_subscriptions" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # listing_id - (optional) is a type of string
  listing_id = var.listing_id

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
output "app_catalog_subscriptions" {
  description = "returns a list of object"
  value       = data.oci_core_app_catalog_subscriptions.this.app_catalog_subscriptions
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_app_catalog_subscriptions.this.id
}

output "this" {
  value = oci_core_app_catalog_subscriptions.this
}
```

[top](#index)