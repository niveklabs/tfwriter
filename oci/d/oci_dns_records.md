# oci_dns_records

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
module "oci_dns_records" {
  source = "./modules/oci/d/oci_dns_records"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # domain - (optional) is a type of string
  domain = null
  # domain_contains - (optional) is a type of string
  domain_contains = null
  # rtype - (optional) is a type of string
  rtype = null
  # sort_by - (optional) is a type of string
  sort_by = null
  # sort_order - (optional) is a type of string
  sort_order = null
  # zone_name_or_id - (required) is a type of string
  zone_name_or_id = null
  # zone_version - (optional) is a type of string
  zone_version = null

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

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_contains" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rtype" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sort_order" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_name_or_id" {
  description = "(required)"
  type        = string
}

variable "zone_version" {
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
data "oci_dns_records" "this" {
  compartment_id  = var.compartment_id
  domain          = var.domain
  domain_contains = var.domain_contains
  rtype           = var.rtype
  sort_by         = var.sort_by
  sort_order      = var.sort_order
  zone_name_or_id = var.zone_name_or_id
  zone_version    = var.zone_version

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
  value       = data.oci_dns_records.this.id
}

output "records" {
  description = "returns a list of object"
  value       = data.oci_dns_records.this.records
}

output "this" {
  value = oci_dns_records.this
}
```

[top](#index)