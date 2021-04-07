# oci_dns_rrset

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
module "oci_dns_rrset" {
  source = "./modules/oci/d/oci_dns_rrset"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # domain - (required) is a type of string
  domain = null
  # rtype - (required) is a type of string
  rtype = null
  # scope - (optional) is a type of string
  scope = null
  # view_id - (optional) is a type of string
  view_id = null
  # zone_name_or_id - (required) is a type of string
  zone_name_or_id = null
  # zone_version - (optional) is a type of string
  zone_version = null
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
  description = "(required)"
  type        = string
}

variable "rtype" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "view_id" {
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
```

[top](#index)

### Datasource

```terraform
data "oci_dns_rrset" "this" {
  # compartment_id - (optional) is a type of string
  compartment_id = var.compartment_id
  # domain - (required) is a type of string
  domain = var.domain
  # rtype - (required) is a type of string
  rtype = var.rtype
  # scope - (optional) is a type of string
  scope = var.scope
  # view_id - (optional) is a type of string
  view_id = var.view_id
  # zone_name_or_id - (required) is a type of string
  zone_name_or_id = var.zone_name_or_id
  # zone_version - (optional) is a type of string
  zone_version = var.zone_version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_dns_rrset.this.id
}

output "items" {
  description = "returns a list of object"
  value       = data.oci_dns_rrset.this.items
}

output "this" {
  value = oci_dns_rrset.this
}
```

[top](#index)