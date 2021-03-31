# oci_marketplace_publications

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_marketplace_publications" {
  source = "./modules/oci/d/oci_marketplace_publications"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # listing_type - (required) is a type of string
  listing_type = null
  # name - (optional) is a type of list of string
  name = []
  # operating_systems - (optional) is a type of list of string
  operating_systems = []
  # publication_id - (optional) is a type of string
  publication_id = null

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

variable "listing_type" {
  description = "(required)"
  type        = string
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

variable "publication_id" {
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
data "oci_marketplace_publications" "this" {
  compartment_id    = var.compartment_id
  listing_type      = var.listing_type
  name              = var.name
  operating_systems = var.operating_systems
  publication_id    = var.publication_id

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
  value       = data.oci_marketplace_publications.this.id
}

output "publications" {
  description = "returns a list of object"
  value       = data.oci_marketplace_publications.this.publications
}

output "this" {
  value = oci_marketplace_publications.this
}
```

[top](#index)