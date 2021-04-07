# opc_compute_machine_image

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
module "opc_compute_machine_image" {
  source = "./modules/opc/r/opc_compute_machine_image"

  # account - (required) is a type of string
  account = null
  # attributes - (optional) is a type of string
  attributes = null
  # description - (optional) is a type of string
  description = null
  # file - (required) is a type of string
  file = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "account" {
  description = "(required)"
  type        = string
}

variable "attributes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "opc_compute_machine_image" "this" {
  # account - (required) is a type of string
  account = var.account
  # attributes - (optional) is a type of string
  attributes = var.attributes
  # description - (optional) is a type of string
  description = var.description
  # file - (required) is a type of string
  file = var.file
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "error_reason" {
  description = "returns a string"
  value       = opc_compute_machine_image.this.error_reason
}

output "hypervisor" {
  description = "returns a map of string"
  value       = opc_compute_machine_image.this.hypervisor
}

output "id" {
  description = "returns a string"
  value       = opc_compute_machine_image.this.id
}

output "image_format" {
  description = "returns a string"
  value       = opc_compute_machine_image.this.image_format
}

output "no_upload" {
  description = "returns a bool"
  value       = opc_compute_machine_image.this.no_upload
}

output "platform" {
  description = "returns a string"
  value       = opc_compute_machine_image.this.platform
}

output "state" {
  description = "returns a string"
  value       = opc_compute_machine_image.this.state
}

output "uri" {
  description = "returns a string"
  value       = opc_compute_machine_image.this.uri
}

output "this" {
  value = opc_compute_machine_image.this
}
```

[top](#index)