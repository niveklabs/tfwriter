# hcloud_volume

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcloud = ">= 1.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_volume" {
  source = "./modules/hcloud/r/hcloud_volume"

  # automount - (optional) is a type of bool
  automount = null
  # format - (optional) is a type of string
  format = null
  # labels - (optional) is a type of map of string
  labels = {}
  # location - (optional) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # server_id - (optional) is a type of number
  server_id = null
  # size - (required) is a type of number
  size = null
}
```

[top](#index)

### Variables

```terraform
variable "automount" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "server_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "size" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_volume" "this" {
  automount = var.automount
  format    = var.format
  labels    = var.labels
  location  = var.location
  name      = var.name
  server_id = var.server_id
  size      = var.size
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = hcloud_volume.this.id
}

output "linux_device" {
  description = "returns a string"
  value       = hcloud_volume.this.linux_device
}

output "location" {
  description = "returns a string"
  value       = hcloud_volume.this.location
}

output "server_id" {
  description = "returns a number"
  value       = hcloud_volume.this.server_id
}

output "this" {
  value = hcloud_volume.this
}
```

[top](#index)