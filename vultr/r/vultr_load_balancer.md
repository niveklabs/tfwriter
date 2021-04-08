# vultr_load_balancer

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/vultr/r/vultr_load_balancer"

  # attached_instances - (optional) is a type of list of string
  attached_instances = []
  # balancing_algorithm - (optional) is a type of string
  balancing_algorithm = null
  # cookie_name - (optional) is a type of string
  cookie_name = null
  # label - (optional) is a type of string
  label = null
  # proxy_protocol - (optional) is a type of bool
  proxy_protocol = null
  # region - (required) is a type of string
  region = null
  # ssl_redirect - (optional) is a type of bool
  ssl_redirect = null

  forwarding_rules = [{
    backend_port      = null
    backend_protocol  = null
    frontend_port     = null
    frontend_protocol = null
    rule_id           = null
  }]

  health_check = [{
    check_interval      = null
    healthy_threshold   = null
    path                = null
    port                = null
    protocol            = null
    response_timeout    = null
    unhealthy_threshold = null
  }]

  ssl = [{
    certificate = null
    chain       = null
    private_key = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "attached_instances" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "balancing_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cookie_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy_protocol" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "ssl_redirect" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "forwarding_rules" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      backend_port      = number
      backend_protocol  = string
      frontend_port     = number
      frontend_protocol = string
      rule_id           = string
    }
  ))
}

variable "health_check" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      check_interval      = number
      healthy_threshold   = number
      path                = string
      port                = number
      protocol            = string
      response_timeout    = number
      unhealthy_threshold = number
    }
  ))
  default = []
}

variable "ssl" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      certificate = string
      chain       = string
      private_key = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vultr_load_balancer" "this" {
  # attached_instances - (optional) is a type of list of string
  attached_instances = var.attached_instances
  # balancing_algorithm - (optional) is a type of string
  balancing_algorithm = var.balancing_algorithm
  # cookie_name - (optional) is a type of string
  cookie_name = var.cookie_name
  # label - (optional) is a type of string
  label = var.label
  # proxy_protocol - (optional) is a type of bool
  proxy_protocol = var.proxy_protocol
  # region - (required) is a type of string
  region = var.region
  # ssl_redirect - (optional) is a type of bool
  ssl_redirect = var.ssl_redirect

  dynamic "forwarding_rules" {
    for_each = var.forwarding_rules
    content {
      # backend_port - (required) is a type of number
      backend_port = forwarding_rules.value["backend_port"]
      # backend_protocol - (required) is a type of string
      backend_protocol = forwarding_rules.value["backend_protocol"]
      # frontend_port - (required) is a type of number
      frontend_port = forwarding_rules.value["frontend_port"]
      # frontend_protocol - (required) is a type of string
      frontend_protocol = forwarding_rules.value["frontend_protocol"]
    }
  }

  dynamic "health_check" {
    for_each = var.health_check
    content {
      # check_interval - (required) is a type of number
      check_interval = health_check.value["check_interval"]
      # healthy_threshold - (required) is a type of number
      healthy_threshold = health_check.value["healthy_threshold"]
      # path - (optional) is a type of string
      path = health_check.value["path"]
      # port - (required) is a type of number
      port = health_check.value["port"]
      # protocol - (required) is a type of string
      protocol = health_check.value["protocol"]
      # response_timeout - (required) is a type of number
      response_timeout = health_check.value["response_timeout"]
      # unhealthy_threshold - (required) is a type of number
      unhealthy_threshold = health_check.value["unhealthy_threshold"]
    }
  }

  dynamic "ssl" {
    for_each = var.ssl
    content {
      # certificate - (required) is a type of string
      certificate = ssl.value["certificate"]
      # chain - (optional) is a type of string
      chain = ssl.value["chain"]
      # private_key - (required) is a type of string
      private_key = ssl.value["private_key"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "balancing_algorithm" {
  description = "returns a string"
  value       = vultr_load_balancer.this.balancing_algorithm
}

output "has_ssl" {
  description = "returns a bool"
  value       = vultr_load_balancer.this.has_ssl
}

output "id" {
  description = "returns a string"
  value       = vultr_load_balancer.this.id
}

output "ipv4" {
  description = "returns a string"
  value       = vultr_load_balancer.this.ipv4
}

output "ipv6" {
  description = "returns a string"
  value       = vultr_load_balancer.this.ipv6
}

output "status" {
  description = "returns a string"
  value       = vultr_load_balancer.this.status
}

output "this" {
  value = vultr_load_balancer.this
}
```

[top](#index)