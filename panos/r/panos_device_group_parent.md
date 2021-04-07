# panos_device_group_parent

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
module "panos_device_group_parent" {
  source = "./modules/panos/r/panos_device_group_parent"

  # device_group - (required) is a type of string
  device_group = null
  # parent - (optional) is a type of string
  parent = null
}
```

[top](#index)

### Variables

```terraform
variable "device_group" {
  description = "(required) - The device group name"
  type        = string
}

variable "parent" {
  description = "(optional) - The device group's parent"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_device_group_parent" "this" {
  # device_group - (required) is a type of string
  device_group = var.device_group
  # parent - (optional) is a type of string
  parent = var.parent
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_device_group_parent.this.id
}

output "this" {
  value = panos_device_group_parent.this
}
```

[top](#index)