# opc_compute_image_list_entry

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_image_list_entry" {
  source = "./modules/opc/d/opc_compute_image_list_entry"

  # entry - (optional) is a type of number
  entry = null
  # image_list - (required) is a type of string
  image_list = null
  # version - (required) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "entry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "image_list" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "opc_compute_image_list_entry" "this" {
  entry      = var.entry
  image_list = var.image_list
  version    = var.version
}
```

[top](#index)

### Outputs

```terraform
output "attributes" {
  description = "returns a string"
  value       = data.opc_compute_image_list_entry.this.attributes
}

output "id" {
  description = "returns a string"
  value       = data.opc_compute_image_list_entry.this.id
}

output "machine_images" {
  description = "returns a list of string"
  value       = data.opc_compute_image_list_entry.this.machine_images
}

output "uri" {
  description = "returns a string"
  value       = data.opc_compute_image_list_entry.this.uri
}

output "this" {
  value = opc_compute_image_list_entry.this
}
```

[top](#index)