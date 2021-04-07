# oci_mysql_shapes

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
module "oci_mysql_shapes" {
  source = "./modules/oci/d/oci_mysql_shapes"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # is_supported_for - (optional) is a type of list of string
  is_supported_for = []
  # name - (optional) is a type of string
  name = null

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

variable "is_supported_for" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
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
data "oci_mysql_shapes" "this" {
  # availability_domain - (optional) is a type of string
  availability_domain = var.availability_domain
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # is_supported_for - (optional) is a type of list of string
  is_supported_for = var.is_supported_for
  # name - (optional) is a type of string
  name = var.name

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
  value       = data.oci_mysql_shapes.this.id
}

output "shapes" {
  description = "returns a list of object"
  value       = data.oci_mysql_shapes.this.shapes
}

output "this" {
  value = oci_mysql_shapes.this
}
```

[top](#index)