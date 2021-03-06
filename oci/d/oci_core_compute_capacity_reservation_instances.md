# oci_core_compute_capacity_reservation_instances

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
module "oci_core_compute_capacity_reservation_instances" {
  source = "./modules/oci/d/oci_core_compute_capacity_reservation_instances"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # capacity_reservation_id - (required) is a type of string
  capacity_reservation_id = null
  # compartment_id - (optional) is a type of string
  compartment_id = null

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

variable "capacity_reservation_id" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
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
data "oci_core_compute_capacity_reservation_instances" "this" {
  # availability_domain - (optional) is a type of string
  availability_domain = var.availability_domain
  # capacity_reservation_id - (required) is a type of string
  capacity_reservation_id = var.capacity_reservation_id
  # compartment_id - (optional) is a type of string
  compartment_id = var.compartment_id

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
output "capacity_reservation_instances" {
  description = "returns a list of object"
  value       = data.oci_core_compute_capacity_reservation_instances.this.capacity_reservation_instances
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_compute_capacity_reservation_instances.this.id
}

output "this" {
  value = oci_core_compute_capacity_reservation_instances.this
}
```

[top](#index)