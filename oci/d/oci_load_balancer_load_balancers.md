# oci_load_balancer_load_balancers

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
module "oci_load_balancer_load_balancers" {
  source = "./modules/oci/d/oci_load_balancer_load_balancers"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # detail - (optional) is a type of string
  detail = null
  # display_name - (optional) is a type of string
  display_name = null
  # state - (optional) is a type of string
  state = null

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

variable "detail" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
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
data "oci_load_balancer_load_balancers" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # detail - (optional) is a type of string
  detail = var.detail
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # state - (optional) is a type of string
  state = var.state

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
  value       = data.oci_load_balancer_load_balancers.this.id
}

output "load_balancers" {
  description = "returns a list of object"
  value       = data.oci_load_balancer_load_balancers.this.load_balancers
}

output "this" {
  value = oci_load_balancer_load_balancers.this
}
```

[top](#index)