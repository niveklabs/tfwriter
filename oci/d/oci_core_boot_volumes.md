# oci_core_boot_volumes

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
module "oci_core_boot_volumes" {
  source = "./modules/oci/d/oci_core_boot_volumes"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # volume_group_id - (optional) is a type of string
  volume_group_id = null

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
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "volume_group_id" {
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
data "oci_core_boot_volumes" "this" {
  # availability_domain - (required) is a type of string
  availability_domain = var.availability_domain
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # volume_group_id - (optional) is a type of string
  volume_group_id = var.volume_group_id

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
output "boot_volumes" {
  description = "returns a list of object"
  value       = data.oci_core_boot_volumes.this.boot_volumes
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_boot_volumes.this.id
}

output "this" {
  value = oci_core_boot_volumes.this
}
```

[top](#index)