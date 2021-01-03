# oci_kms_keys

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
module "oci_kms_keys" {
  source = "./modules/oci/d/oci_kms_keys"

  # algorithm - (optional) is a type of string
  algorithm = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # length - (optional) is a type of number
  length = null
  # management_endpoint - (required) is a type of string
  management_endpoint = null
  # protection_mode - (optional) is a type of string
  protection_mode = null

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
variable "algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "management_endpoint" {
  description = "(required)"
  type        = string
}

variable "protection_mode" {
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
data "oci_kms_keys" "this" {
  algorithm           = var.algorithm
  compartment_id      = var.compartment_id
  length              = var.length
  management_endpoint = var.management_endpoint
  protection_mode     = var.protection_mode

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
  value       = data.oci_kms_keys.this.id
}

output "keys" {
  description = "returns a list of object"
  value       = data.oci_kms_keys.this.keys
}

output "this" {
  value = oci_kms_keys.this
}
```

[top](#index)