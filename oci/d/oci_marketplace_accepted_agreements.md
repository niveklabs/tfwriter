# oci_marketplace_accepted_agreements

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
module "oci_marketplace_accepted_agreements" {
  source = "./modules/oci/d/oci_marketplace_accepted_agreements"

  # accepted_agreement_id - (optional) is a type of string
  accepted_agreement_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # listing_id - (optional) is a type of string
  listing_id = null
  # package_version - (optional) is a type of string
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
variable "accepted_agreement_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "listing_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "package_version" {
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
data "oci_marketplace_accepted_agreements" "this" {
  accepted_agreement_id = var.accepted_agreement_id
  compartment_id        = var.compartment_id
  display_name          = var.display_name
  listing_id            = var.listing_id
  package_version       = var.package_version

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
output "accepted_agreements" {
  description = "returns a list of object"
  value       = data.oci_marketplace_accepted_agreements.this.accepted_agreements
}

output "id" {
  description = "returns a string"
  value       = data.oci_marketplace_accepted_agreements.this.id
}

output "this" {
  value = oci_marketplace_accepted_agreements.this
}
```

[top](#index)