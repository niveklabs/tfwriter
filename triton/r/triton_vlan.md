# triton_vlan

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
module "triton_vlan" {
  source = "./modules/triton/r/triton_vlan"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # vlan_id - (required) is a type of number
  vlan_id = null

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
variable "description" {
  description = "(optional) - Description of the VLAN"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Unique name to identify VLAN"
  type        = string
}

variable "vlan_id" {
  description = "(required) - Number between 0-4095 indicating VLAN ID"
  type        = number
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
resource "triton_vlan" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # vlan_id - (required) is a type of number
  vlan_id = var.vlan_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
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
  value       = triton_vlan.this.id
}

output "this" {
  value = triton_vlan.this
}
```

[top](#index)