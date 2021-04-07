# oci_limits_limit_definitions

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
module "oci_limits_limit_definitions" {
  source = "./modules/oci/d/oci_limits_limit_definitions"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # name - (optional) is a type of string
  name = null
  # service_name - (optional) is a type of string
  service_name = null

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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
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
data "oci_limits_limit_definitions" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # name - (optional) is a type of string
  name = var.name
  # service_name - (optional) is a type of string
  service_name = var.service_name

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
  value       = data.oci_limits_limit_definitions.this.id
}

output "limit_definitions" {
  description = "returns a list of object"
  value       = data.oci_limits_limit_definitions.this.limit_definitions
}

output "this" {
  value = oci_limits_limit_definitions.this
}
```

[top](#index)