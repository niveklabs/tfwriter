# triton_service_group

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    triton = ">= 0.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "triton_service_group" {
  source = "./modules/triton/r/triton_service_group"

  # capacity - (optional) is a type of number
  capacity = null
  # group_name - (required) is a type of string
  group_name = null
  # template - (required) is a type of string
  template = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "capacity" {
  description = "(optional) - Number of instances to launch and monitor"
  type        = number
  default     = null
}

variable "group_name" {
  description = "(required) - Friendly name for the service group"
  type        = string
}

variable "template" {
  description = "(required) - Identifier of an instance template"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "triton_service_group" "this" {
  capacity   = var.capacity
  group_name = var.group_name
  template   = var.template

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "capacity" {
  description = "returns a number"
  value       = triton_service_group.this.capacity
}

output "id" {
  description = "returns a string"
  value       = triton_service_group.this.id
}

output "this" {
  value = triton_service_group.this
}
```

[top](#index)