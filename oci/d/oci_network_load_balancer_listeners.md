# oci_network_load_balancer_listeners

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
module "oci_network_load_balancer_listeners" {
  source = "./modules/oci/d/oci_network_load_balancer_listeners"

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
data "oci_network_load_balancer_listeners" "this" {
  # network_load_balancer_id - (required) is a type of string
  network_load_balancer_id = var.network_load_balancer_id

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
  value       = data.oci_network_load_balancer_listeners.this.id
}

output "listener_collection" {
  description = "returns a list of object"
  value       = data.oci_network_load_balancer_listeners.this.listener_collection
}

output "this" {
  value = oci_network_load_balancer_listeners.this
}
```

[top](#index)