# panos_panorama_device_group

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_device_group" {
  source = "./modules/panos/r/panos_panorama_device_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  device = [{
    serial    = null
    vsys_list = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "device" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      serial    = string
      vsys_list = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_device_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name

  dynamic "device" {
    for_each = var.device
    content {
      # serial - (required) is a type of string
      serial = device.value["serial"]
      # vsys_list - (optional) is a type of set of string
      vsys_list = device.value["vsys_list"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_device_group.this.id
}

output "this" {
  value = panos_panorama_device_group.this
}
```

[top](#index)