# opc_compute_image_list_entry

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_image_list_entry" {
  source = "./modules/opc/r/opc_compute_image_list_entry"

  # attributes - (optional) is a type of string
  attributes = null
  # machine_images - (required) is a type of list of string
  machine_images = []
  # name - (required) is a type of string
  name = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "attributes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "machine_images" {
  description = "(required)"
  type        = list(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_image_list_entry" "this" {
  # attributes - (optional) is a type of string
  attributes = var.attributes
  # machine_images - (required) is a type of list of string
  machine_images = var.machine_images
  # name - (required) is a type of string
  name = var.name
  # version - (required) is a type of number
  version = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opc_compute_image_list_entry.this.id
}

output "uri" {
  description = "returns a string"
  value       = opc_compute_image_list_entry.this.uri
}

output "this" {
  value = opc_compute_image_list_entry.this
}
```

[top](#index)