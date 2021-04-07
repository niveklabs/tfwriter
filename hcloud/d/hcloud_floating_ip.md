# hcloud_floating_ip

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
    hcloud = ">= 1.26.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_floating_ip" {
  source = "./modules/hcloud/d/hcloud_floating_ip"

  # ip_address - (optional) is a type of string
  ip_address = null
  # name - (optional) is a type of string
  name = null
  # selector - (optional) is a type of string
  selector = null
  # with_selector - (optional) is a type of string
  with_selector = null
}
```

[top](#index)

### Variables

```terraform
variable "ip_address" {
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

variable "with_selector" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "hcloud_floating_ip" "this" {
  # ip_address - (optional) is a type of string
  ip_address = var.ip_address
  # name - (optional) is a type of string
  name = var.name
  # selector - (optional) is a type of string
  selector = var.selector
  # with_selector - (optional) is a type of string
  with_selector = var.with_selector
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.hcloud_floating_ip.this.description
}

output "home_location" {
  description = "returns a string"
  value       = data.hcloud_floating_ip.this.home_location
}

output "id" {
  description = "returns a number"
  value       = data.hcloud_floating_ip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.hcloud_floating_ip.this.ip_address
}

output "ip_network" {
  description = "returns a string"
  value       = data.hcloud_floating_ip.this.ip_network
}

output "labels" {
  description = "returns a map of string"
  value       = data.hcloud_floating_ip.this.labels
}

output "server_id" {
  description = "returns a number"
  value       = data.hcloud_floating_ip.this.server_id
}

output "type" {
  description = "returns a string"
  value       = data.hcloud_floating_ip.this.type
}

output "this" {
  value = hcloud_floating_ip.this
}
```

[top](#index)