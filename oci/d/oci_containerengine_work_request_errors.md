# oci_containerengine_work_request_errors

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
module "oci_containerengine_work_request_errors" {
  source = "./modules/oci/d/oci_containerengine_work_request_errors"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # work_request_id - (required) is a type of string
  work_request_id = null

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
  description = "(required)"
  type        = string
}

variable "work_request_id" {
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
data "oci_containerengine_work_request_errors" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # work_request_id - (required) is a type of string
  work_request_id = var.work_request_id

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
  value       = data.oci_containerengine_work_request_errors.this.id
}

output "work_request_errors" {
  description = "returns a list of object"
  value       = data.oci_containerengine_work_request_errors.this.work_request_errors
}

output "this" {
  value = oci_containerengine_work_request_errors.this
}
```

[top](#index)