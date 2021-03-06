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
    oci = ">= 4.21.0"
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
  # curve_id - (optional) is a type of string
  curve_id = null
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

variable "curve_id" {
  description = "(optional)"
  type        = string
  default     = null
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
  # algorithm - (optional) is a type of string
  algorithm = var.algorithm
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # curve_id - (optional) is a type of string
  curve_id = var.curve_id
  # length - (optional) is a type of number
  length = var.length
  # management_endpoint - (required) is a type of string
  management_endpoint = var.management_endpoint
  # protection_mode - (optional) is a type of string
  protection_mode = var.protection_mode

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