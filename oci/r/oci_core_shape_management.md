# oci_core_shape_management

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "oci_core_shape_management" {
  source = "./modules/oci/r/oci_core_shape_management"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # image_id - (required) is a type of string
  image_id = null
  # shape_name - (required) is a type of string
  shape_name = null

  timeouts = [{
    create = null
    delete = null
    update = null
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

variable "image_id" {
  description = "(required)"
  type        = string
}

variable "shape_name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_core_shape_management" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # image_id - (required) is a type of string
  image_id = var.image_id
  # shape_name - (required) is a type of string
  shape_name = var.shape_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = oci_core_shape_management.this.id
}

output "this" {
  value = oci_core_shape_management.this
}
```

[top](#index)