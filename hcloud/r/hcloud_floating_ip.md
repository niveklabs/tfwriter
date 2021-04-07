# hcloud_floating_ip

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
    hcloud = ">= 1.26.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_floating_ip" {
  source = "./modules/hcloud/r/hcloud_floating_ip"

  # description - (optional) is a type of string
  description = null
  # home_location - (optional) is a type of string
  home_location = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (optional) is a type of string
  name = null
  # server_id - (optional) is a type of number
  server_id = null
  # type - (required) is a type of string
  type = null
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

variable "home_location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_floating_ip" "this" {
  # description - (optional) is a type of string
  description = var.description
  # home_location - (optional) is a type of string
  home_location = var.home_location
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (optional) is a type of string
  name = var.name
  # server_id - (optional) is a type of number
  server_id = var.server_id
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "home_location" {
  description = "returns a string"
  value       = hcloud_floating_ip.this.home_location
}

output "id" {
  description = "returns a string"
  value       = hcloud_floating_ip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = hcloud_floating_ip.this.ip_address
}

output "ip_network" {
  description = "returns a string"
  value       = hcloud_floating_ip.this.ip_network
}

output "name" {
  description = "returns a string"
  value       = hcloud_floating_ip.this.name
}

output "server_id" {
  description = "returns a number"
  value       = hcloud_floating_ip.this.server_id
}

output "this" {
  value = hcloud_floating_ip.this
}
```

[top](#index)