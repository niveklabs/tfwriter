# oci_load_balancer_path_route_sets

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
module "oci_load_balancer_path_route_sets" {
  source = "./modules/oci/d/oci_load_balancer_path_route_sets"

  # load_balancer_id - (required) is a type of string
  load_balancer_id = null

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
variable "load_balancer_id" {
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
data "oci_load_balancer_path_route_sets" "this" {
  # load_balancer_id - (required) is a type of string
  load_balancer_id = var.load_balancer_id

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
  value       = data.oci_load_balancer_path_route_sets.this.id
}

output "path_route_sets" {
  description = "returns a list of object"
  value       = data.oci_load_balancer_path_route_sets.this.path_route_sets
}

output "this" {
  value = oci_load_balancer_path_route_sets.this
}
```

[top](#index)