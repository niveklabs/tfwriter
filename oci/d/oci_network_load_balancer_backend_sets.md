# oci_network_load_balancer_backend_sets

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
module "oci_network_load_balancer_backend_sets" {
  source = "./modules/oci/d/oci_network_load_balancer_backend_sets"

  # network_load_balancer_id - (required) is a type of string
  network_load_balancer_id = null

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
variable "network_load_balancer_id" {
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
data "oci_network_load_balancer_backend_sets" "this" {
  network_load_balancer_id = var.network_load_balancer_id

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
output "backend_set_collection" {
  description = "returns a list of object"
  value       = data.oci_network_load_balancer_backend_sets.this.backend_set_collection
}

output "id" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_backend_sets.this.id
}

output "this" {
  value = oci_network_load_balancer_backend_sets.this
}
```

[top](#index)