# aviatrix_device_tag

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_device_tag" {
  source = "./modules/aviatrix/r/aviatrix_device_tag"

  # config - (required) is a type of string
  config = null
  # device_names - (required) is a type of list of string
  device_names = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "config" {
  description = "(required) - Config to apply to devices that are attached to the tag."
  type        = string
}

variable "device_names" {
  description = "(required) - List of device names to attach to this tag."
  type        = list(string)
}

variable "name" {
  description = "(required) - Name of the tag."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_device_tag" "this" {
  config       = var.config
  device_names = var.device_names
  name         = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_device_tag.this.id
}

output "this" {
  value = aviatrix_device_tag.this
}
```

[top](#index)