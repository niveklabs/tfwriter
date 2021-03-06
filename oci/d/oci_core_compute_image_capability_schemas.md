# oci_core_compute_image_capability_schemas

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
module "oci_core_compute_image_capability_schemas" {
  source = "./modules/oci/d/oci_core_compute_image_capability_schemas"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # image_id - (optional) is a type of string
  image_id = null

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

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_id" {
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
data "oci_core_compute_image_capability_schemas" "this" {
  # compartment_id - (optional) is a type of string
  compartment_id = var.compartment_id
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # image_id - (optional) is a type of string
  image_id = var.image_id

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
output "compute_image_capability_schemas" {
  description = "returns a list of object"
  value       = data.oci_core_compute_image_capability_schemas.this.compute_image_capability_schemas
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_compute_image_capability_schemas.this.id
}

output "this" {
  value = oci_core_compute_image_capability_schemas.this
}
```

[top](#index)