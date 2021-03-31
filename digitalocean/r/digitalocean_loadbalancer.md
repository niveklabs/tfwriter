# digitalocean_loadbalancer

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_loadbalancer" {
  source = "./modules/digitalocean/r/digitalocean_loadbalancer"

  # algorithm - (optional) is a type of string
  algorithm = null
  # droplet_ids - (optional) is a type of set of number
  droplet_ids = []
  # droplet_tag - (optional) is a type of string
  droplet_tag = null
  # enable_backend_keepalive - (optional) is a type of bool
  enable_backend_keepalive = null
  # enable_proxy_protocol - (optional) is a type of bool
  enable_proxy_protocol = null
  # name - (required) is a type of string
  name = null
  # redirect_http_to_https - (optional) is a type of bool
  redirect_http_to_https = null
  # region - (required) is a type of string
  region = null
  # size - (optional) is a type of string
  size = null
  # vpc_uuid - (optional) is a type of string
  vpc_uuid = null

  forwarding_rule = [{
    certificate_id   = null
    certificate_name = null
    entry_port       = null
    entry_protocol   = null
    target_port      = null
    target_protocol  = null
    tls_passthrough  = null
  }]

  healthcheck = [{
    check_interval_seconds   = null
    healthy_threshold        = null
    path                     = null
    port                     = null
    protocol                 = null
    response_timeout_seconds = null
    unhealthy_threshold      = null
  }]

  sticky_sessions = [{
    cookie_name        = null
    cookie_ttl_seconds = null
    type               = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "droplet_ids" {
  description = "(optional)"
  type        = set(number)
  default     = null
}

variable "droplet_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_backend_keepalive" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_proxy_protocol" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "redirect_http_to_https" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "size" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forwarding_rule" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      certificate_id   = string
      certificate_name = string
      entry_port       = number
      entry_protocol   = string
      target_port      = number
      target_protocol  = string
      tls_passthrough  = bool
    }
  ))
}

variable "healthcheck" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      check_interval_seconds   = number
      healthy_threshold        = number
      path                     = string
      port                     = number
      protocol                 = string
      response_timeout_seconds = number
      unhealthy_threshold      = number
    }
  ))
  default = []
}

variable "sticky_sessions" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cookie_name        = string
      cookie_ttl_seconds = number
      type               = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_loadbalancer" "this" {
  algorithm                = var.algorithm
  droplet_ids              = var.droplet_ids
  droplet_tag              = var.droplet_tag
  enable_backend_keepalive = var.enable_backend_keepalive
  enable_proxy_protocol    = var.enable_proxy_protocol
  name                     = var.name
  redirect_http_to_https   = var.redirect_http_to_https
  region                   = var.region
  size                     = var.size
  vpc_uuid                 = var.vpc_uuid

  dynamic "forwarding_rule" {
    for_each = var.forwarding_rule
    content {
      certificate_id   = forwarding_rule.value["certificate_id"]
      certificate_name = forwarding_rule.value["certificate_name"]
      entry_port       = forwarding_rule.value["entry_port"]
      entry_protocol   = forwarding_rule.value["entry_protocol"]
      target_port      = forwarding_rule.value["target_port"]
      target_protocol  = forwarding_rule.value["target_protocol"]
      tls_passthrough  = forwarding_rule.value["tls_passthrough"]
    }
  }

  dynamic "healthcheck" {
    for_each = var.healthcheck
    content {
      check_interval_seconds   = healthcheck.value["check_interval_seconds"]
      healthy_threshold        = healthcheck.value["healthy_threshold"]
      path                     = healthcheck.value["path"]
      port                     = healthcheck.value["port"]
      protocol                 = healthcheck.value["protocol"]
      response_timeout_seconds = healthcheck.value["response_timeout_seconds"]
      unhealthy_threshold      = healthcheck.value["unhealthy_threshold"]
    }
  }

  dynamic "sticky_sessions" {
    for_each = var.sticky_sessions
    content {
      cookie_name        = sticky_sessions.value["cookie_name"]
      cookie_ttl_seconds = sticky_sessions.value["cookie_ttl_seconds"]
      type               = sticky_sessions.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "droplet_ids" {
  description = "returns a set of number"
  value       = digitalocean_loadbalancer.this.droplet_ids
}

output "id" {
  description = "returns a string"
  value       = digitalocean_loadbalancer.this.id
}

output "ip" {
  description = "returns a string"
  value       = digitalocean_loadbalancer.this.ip
}

output "status" {
  description = "returns a string"
  value       = digitalocean_loadbalancer.this.status
}

output "urn" {
  description = "returns a string"
  value       = digitalocean_loadbalancer.this.urn
}

output "vpc_uuid" {
  description = "returns a string"
  value       = digitalocean_loadbalancer.this.vpc_uuid
}

output "this" {
  value = digitalocean_loadbalancer.this
}
```

[top](#index)