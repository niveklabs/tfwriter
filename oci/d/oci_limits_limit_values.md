# oci_limits_limit_values

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_limits_limit_values" {
  source = "./modules/oci/d/oci_limits_limit_values"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # name - (optional) is a type of string
  name = null
  # scope_type - (optional) is a type of string
  scope_type = null
  # service_name - (required) is a type of string
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
variable "availability_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
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
data "oci_limits_limit_values" "this" {
  availability_domain = var.availability_domain
  compartment_id      = var.compartment_id
  name                = var.name
  scope_type          = var.scope_type
  service_name        = var.service_name

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
  value       = data.oci_limits_limit_values.this.id
}

output "limit_values" {
  description = "returns a list of object"
  value       = data.oci_limits_limit_values.this.limit_values
}

output "this" {
  value = oci_limits_limit_values.this
}
```

[top](#index)