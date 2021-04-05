# panos_panorama_template

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
module "panos_panorama_template" {
  source = "./modules/panos/r/panos_panorama_template"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  devices = [{
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

variable "devices" {
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
resource "panos_panorama_template" "this" {
  description = var.description
  name        = var.name

  dynamic "devices" {
    for_each = var.devices
    content {
      serial    = devices.value["serial"]
      vsys_list = devices.value["vsys_list"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_vsys" {
  description = "returns a string"
  value       = panos_panorama_template.this.default_vsys
}

output "id" {
  description = "returns a string"
  value       = panos_panorama_template.this.id
}

output "this" {
  value = panos_panorama_template.this
}
```

[top](#index)