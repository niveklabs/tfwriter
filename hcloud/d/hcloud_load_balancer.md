# hcloud_load_balancer

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
module "hcloud_load_balancer" {
  source = "./modules/hcloud/d/hcloud_load_balancer"

  # name - (optional) is a type of string
  name = null
  # with_selector - (optional) is a type of string
  with_selector = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
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
data "hcloud_load_balancer" "this" {
  name          = var.name
  with_selector = var.with_selector
}
```

[top](#index)

### Outputs

```terraform
output "algorithm" {
  description = "returns a list of object"
  value       = data.hcloud_load_balancer.this.algorithm
}

output "id" {
  description = "returns a number"
  value       = data.hcloud_load_balancer.this.id
}

output "ipv4" {
  description = "returns a string"
  value       = data.hcloud_load_balancer.this.ipv4
}

output "ipv6" {
  description = "returns a string"
  value       = data.hcloud_load_balancer.this.ipv6
}

output "labels" {
  description = "returns a map of string"
  value       = data.hcloud_load_balancer.this.labels
}

output "load_balancer_type" {
  description = "returns a string"
  value       = data.hcloud_load_balancer.this.load_balancer_type
}

output "location" {
  description = "returns a string"
  value       = data.hcloud_load_balancer.this.location
}

output "network_zone" {
  description = "returns a string"
  value       = data.hcloud_load_balancer.this.network_zone
}

output "service" {
  description = "returns a list of object"
  value       = data.hcloud_load_balancer.this.service
}

output "target" {
  description = "returns a list of object"
  value       = data.hcloud_load_balancer.this.target
}

output "this" {
  value = hcloud_load_balancer.this
}
```

[top](#index)