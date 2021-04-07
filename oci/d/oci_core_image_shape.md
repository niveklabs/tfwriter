# oci_core_image_shape

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
module "oci_core_image_shape" {
  source = "./modules/oci/d/oci_core_image_shape"

  # image_id - (required) is a type of string
  image_id = null
  # shape_name - (required) is a type of string
  shape_name = null
}
```

[top](#index)

### Variables

```terraform
variable "image_id" {
  description = "(required)"
  type        = string
}

variable "shape_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_core_image_shape" "this" {
  image_id   = var.image_id
  shape_name = var.shape_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_core_image_shape.this.id
}

output "memory_constraints" {
  description = "returns a list of object"
  value       = data.oci_core_image_shape.this.memory_constraints
}

output "ocpu_constraints" {
  description = "returns a list of object"
  value       = data.oci_core_image_shape.this.ocpu_constraints
}

output "shape" {
  description = "returns a string"
  value       = data.oci_core_image_shape.this.shape
}

output "this" {
  value = oci_core_image_shape.this
}
```

[top](#index)