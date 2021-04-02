# oci_network_load_balancer_listener

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "oci_network_load_balancer_listener" {
  source = "./modules/oci/r/oci_network_load_balancer_listener"

  # default_backend_set_name - (required) is a type of string
  default_backend_set_name = null
  # name - (required) is a type of string
  name = null
  # network_load_balancer_id - (required) is a type of string
  network_load_balancer_id = null
  # port - (required) is a type of number
  port = null
  # protocol - (required) is a type of string
  protocol = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_backend_set_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_network_load_balancer_listener" "this" {
  default_backend_set_name = var.default_backend_set_name
  name                     = var.name
  network_load_balancer_id = var.network_load_balancer_id
  port                     = var.port
  protocol                 = var.protocol

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = oci_network_load_balancer_listener.this.id
}

output "this" {
  value = oci_network_load_balancer_listener.this
}
```

[top](#index)