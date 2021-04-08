# vultr_load_balancer

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_load_balancer" {
  source = "./modules/vultr/d/vultr_load_balancer"

  # proxy_protocol - (optional) is a type of bool
  proxy_protocol = null

  filter = [{
    name   = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "proxy_protocol" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vultr_load_balancer" "this" {
  # proxy_protocol - (optional) is a type of bool
  proxy_protocol = var.proxy_protocol

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # values - (required) is a type of list of string
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "attached_instances" {
  description = "returns a list of string"
  value       = data.vultr_load_balancer.this.attached_instances
}

output "balancing_algorithm" {
  description = "returns a string"
  value       = data.vultr_load_balancer.this.balancing_algorithm
}

output "cookie_name" {
  description = "returns a string"
  value       = data.vultr_load_balancer.this.cookie_name
}

output "date_created" {
  description = "returns a string"
  value       = data.vultr_load_balancer.this.date_created
}

output "forwarding_rules" {
  description = "returns a list of map of string"
  value       = data.vultr_load_balancer.this.forwarding_rules
}

output "has_ssl" {
  description = "returns a bool"
  value       = data.vultr_load_balancer.this.has_ssl
}

output "health_check" {
  description = "returns a map of string"
  value       = data.vultr_load_balancer.this.health_check
}

output "id" {
  description = "returns a string"
  value       = data.vultr_load_balancer.this.id
}

output "ipv4" {
  description = "returns a string"
  value       = data.vultr_load_balancer.this.ipv4
}

output "ipv6" {
  description = "returns a string"
  value       = data.vultr_load_balancer.this.ipv6
}

output "label" {
  description = "returns a string"
  value       = data.vultr_load_balancer.this.label
}

output "region" {
  description = "returns a string"
  value       = data.vultr_load_balancer.this.region
}

output "ssl" {
  description = "returns a map of string"
  value       = data.vultr_load_balancer.this.ssl
}

output "ssl_redirect" {
  description = "returns a bool"
  value       = data.vultr_load_balancer.this.ssl_redirect
}

output "status" {
  description = "returns a string"
  value       = data.vultr_load_balancer.this.status
}

output "this" {
  value = vultr_load_balancer.this
}
```

[top](#index)