# oci_load_balancer_load_balancer_routing_policy

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
module "oci_load_balancer_load_balancer_routing_policy" {
  source = "./modules/oci/r/oci_load_balancer_load_balancer_routing_policy"

  # condition_language_version - (required) is a type of string
  condition_language_version = null
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # name - (required) is a type of string
  name = null

  rules = [{
    actions = [{
      backend_set_name = null
      name             = null
    }]
    condition = null
    name      = null
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
variable "condition_language_version" {
  description = "(required)"
  type        = string
}

variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rules" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      actions = list(object(
        {
          backend_set_name = string
          name             = string
        }
      ))
      condition = string
      name      = string
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
resource "oci_load_balancer_load_balancer_routing_policy" "this" {
  condition_language_version = var.condition_language_version
  load_balancer_id           = var.load_balancer_id
  name                       = var.name

  dynamic "rules" {
    for_each = var.rules
    content {
      condition = rules.value["condition"]
      name      = rules.value["name"]

      dynamic "actions" {
        for_each = rules.value.actions
        content {
          backend_set_name = actions.value["backend_set_name"]
          name             = actions.value["name"]
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
  value       = oci_load_balancer_load_balancer_routing_policy.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_load_balancer_load_balancer_routing_policy.this.state
}

output "this" {
  value = oci_load_balancer_load_balancer_routing_policy.this
}
```

[top](#index)