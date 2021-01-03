# opc_compute_machine_image

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
module "opc_compute_machine_image" {
  source = "./modules/opc/d/opc_compute_machine_image"

  # account - (required) is a type of string
  account = null
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

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "opc_compute_machine_image" "this" {
  account = var.account
  name    = var.name
}
```

[top](#index)

### Outputs

```terraform
output "attributes" {
  description = "returns a string"
  value       = data.opc_compute_machine_image.this.attributes
}

output "description" {
  description = "returns a string"
  value       = data.opc_compute_machine_image.this.description
}

output "error_reason" {
  description = "returns a string"
  value       = data.opc_compute_machine_image.this.error_reason
}

output "file" {
  description = "returns a string"
  value       = data.opc_compute_machine_image.this.file
}

output "hypervisor" {
  description = "returns a map of string"
  value       = data.opc_compute_machine_image.this.hypervisor
}

output "id" {
  description = "returns a string"
  value       = data.opc_compute_machine_image.this.id
}

output "image_format" {
  description = "returns a string"
  value       = data.opc_compute_machine_image.this.image_format
}

output "no_upload" {
  description = "returns a bool"
  value       = data.opc_compute_machine_image.this.no_upload
}

output "platform" {
  description = "returns a string"
  value       = data.opc_compute_machine_image.this.platform
}

output "sizes" {
  description = "returns a map of string"
  value       = data.opc_compute_machine_image.this.sizes
}

output "state" {
  description = "returns a string"
  value       = data.opc_compute_machine_image.this.state
}

output "uri" {
  description = "returns a string"
  value       = data.opc_compute_machine_image.this.uri
}

output "this" {
  value = opc_compute_machine_image.this
}
```

[top](#index)