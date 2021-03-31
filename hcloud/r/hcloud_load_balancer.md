# hcloud_load_balancer

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
module "hcloud_load_balancer" {
  source = "./modules/hcloud/r/hcloud_load_balancer"

  # labels - (optional) is a type of map of string
  labels = {}
  # load_balancer_type - (required) is a type of string
  load_balancer_type = null
  # location - (optional) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # network_zone - (optional) is a type of string
  network_zone = null

  algorithm = [{
    type = null
  }]

  target = [{
    server_id      = null
    type           = null
    use_private_ip = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "load_balancer_type" {
  description = "(required)"
  type        = string
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

variable "network_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "algorithm" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      type = string
    }
  ))
  default = []
}

variable "target" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      server_id      = number
      type           = string
      use_private_ip = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_load_balancer" "this" {
  labels             = var.labels
  load_balancer_type = var.load_balancer_type
  location           = var.location
  name               = var.name
  network_zone       = var.network_zone

  dynamic "algorithm" {
    for_each = var.algorithm
    content {
      type = algorithm.value["type"]
    }
  }

  dynamic "target" {
    for_each = var.target
    content {
      server_id      = target.value["server_id"]
      type           = target.value["type"]
      use_private_ip = target.value["use_private_ip"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = hcloud_load_balancer.this.id
}

output "ipv4" {
  description = "returns a string"
  value       = hcloud_load_balancer.this.ipv4
}

output "ipv6" {
  description = "returns a string"
  value       = hcloud_load_balancer.this.ipv6
}

output "labels" {
  description = "returns a map of string"
  value       = hcloud_load_balancer.this.labels
}

output "location" {
  description = "returns a string"
  value       = hcloud_load_balancer.this.location
}

output "network_id" {
  description = "returns a number"
  value       = hcloud_load_balancer.this.network_id
}

output "network_ip" {
  description = "returns a string"
  value       = hcloud_load_balancer.this.network_ip
}

output "network_zone" {
  description = "returns a string"
  value       = hcloud_load_balancer.this.network_zone
}

output "this" {
  value = hcloud_load_balancer.this
}
```

[top](#index)