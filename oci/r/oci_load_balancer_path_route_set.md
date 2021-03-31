# oci_load_balancer_path_route_set

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_load_balancer_path_route_set" {
  source = "./modules/oci/r/oci_load_balancer_path_route_set"

  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # name - (required) is a type of string
  name = null

  path_routes = [{
    backend_set_name = null
    path             = null
    path_match_type = [{
      match_type = null
    }]
  }]

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
variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "path_routes" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      backend_set_name = string
      path             = string
      path_match_type = list(object(
        {
          match_type = string
        }
      ))
    }
  ))
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
resource "oci_load_balancer_path_route_set" "this" {
  load_balancer_id = var.load_balancer_id
  name             = var.name

  dynamic "path_routes" {
    for_each = var.path_routes
    content {
      backend_set_name = path_routes.value["backend_set_name"]
      path             = path_routes.value["path"]

      dynamic "path_match_type" {
        for_each = path_routes.value.path_match_type
        content {
          match_type = path_match_type.value["match_type"]
        }
      }

    }
  }

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
  value       = oci_load_balancer_path_route_set.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_load_balancer_path_route_set.this.state
}

output "this" {
  value = oci_load_balancer_path_route_set.this
}
```

[top](#index)