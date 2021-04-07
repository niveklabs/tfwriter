# oci_core_fast_connect_provider_services

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
module "oci_core_fast_connect_provider_services" {
  source = "./modules/oci/d/oci_core_fast_connect_provider_services"

  # compartment_id - (required) is a type of string
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
variable "compartment_id" {
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
data "oci_core_fast_connect_provider_services" "this" {
  # compartment_id - (required) is a type of string
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
output "fast_connect_provider_services" {
  description = "returns a list of object"
  value       = data.oci_core_fast_connect_provider_services.this.fast_connect_provider_services
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_fast_connect_provider_services.this.id
}

output "this" {
  value = oci_core_fast_connect_provider_services.this
}
```

[top](#index)