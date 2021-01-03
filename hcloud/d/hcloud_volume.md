# hcloud_volume

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/hcloud/d/hcloud_volume"

  # location - (optional) is a type of string
  location = null
  # name - (optional) is a type of string
  name = null
  # selector - (optional) is a type of string
  selector = null
  # server - (optional) is a type of string
  server = null
  # with_selector - (optional) is a type of string
  with_selector = null
  # with_status - (optional) is a type of list of string
  with_status = []
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "selector" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "with_selector" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "with_status" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "hcloud_volume" "this" {
  location      = var.location
  name          = var.name
  selector      = var.selector
  server        = var.server
  with_selector = var.with_selector
  with_status   = var.with_status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a number"
  value       = data.hcloud_volume.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.hcloud_volume.this.labels
}

output "linux_device" {
  description = "returns a string"
  value       = data.hcloud_volume.this.linux_device
}

output "name" {
  description = "returns a string"
  value       = data.hcloud_volume.this.name
}

output "size" {
  description = "returns a number"
  value       = data.hcloud_volume.this.size
}

output "this" {
  value = hcloud_volume.this
}
```

[top](#index)