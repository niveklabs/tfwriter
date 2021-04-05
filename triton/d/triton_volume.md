# triton_volume

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "triton_volume" {
  source = "./modules/triton/d/triton_volume"

  # filesystem_path - (optional) is a type of string
  filesystem_path = null
  # name - (optional) is a type of string
  name = null
  # size - (optional) is a type of number
  size = null
  # state - (optional) is a type of string
  state = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "filesystem_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional) - Type of volume"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "triton_volume" "this" {
  filesystem_path = var.filesystem_path
  name            = var.name
  size            = var.size
  state           = var.state
  tags            = var.tags
  type            = var.type
}
```

[top](#index)

### Outputs

```terraform
output "filesystem_path" {
  description = "returns a string"
  value       = data.triton_volume.this.filesystem_path
}

output "id" {
  description = "returns a string"
  value       = data.triton_volume.this.id
}

output "name" {
  description = "returns a string"
  value       = data.triton_volume.this.name
}

output "networks" {
  description = "returns a list of string"
  value       = data.triton_volume.this.networks
}

output "size" {
  description = "returns a number"
  value       = data.triton_volume.this.size
}

output "state" {
  description = "returns a string"
  value       = data.triton_volume.this.state
}

output "tags" {
  description = "returns a map of string"
  value       = data.triton_volume.this.tags
}

output "type" {
  description = "returns a string"
  value       = data.triton_volume.this.type
}

output "this" {
  value = triton_volume.this
}
```

[top](#index)