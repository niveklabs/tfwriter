# oci_core_public_ips

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_public_ips" {
  source = "./modules/oci/d/oci_core_public_ips"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # lifetime - (optional) is a type of string
  lifetime = null
  # public_ip_pool_id - (optional) is a type of string
  public_ip_pool_id = null
  # scope - (required) is a type of string
  scope = null

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
variable "availability_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "lifetime" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_ip_pool_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
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
data "oci_core_public_ips" "this" {
  availability_domain = var.availability_domain
  compartment_id      = var.compartment_id
  lifetime            = var.lifetime
  public_ip_pool_id   = var.public_ip_pool_id
  scope               = var.scope

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
  value       = data.oci_core_public_ips.this.id
}

output "public_ips" {
  description = "returns a list of object"
  value       = data.oci_core_public_ips.this.public_ips
}

output "this" {
  value = oci_core_public_ips.this
}
```

[top](#index)