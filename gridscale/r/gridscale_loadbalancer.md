# gridscale_loadbalancer

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gridscale = ">= 1.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_loadbalancer" {
  source = "./modules/gridscale/r/gridscale_loadbalancer"

  # algorithm - (required) is a type of string
  algorithm = null
  # labels - (optional) is a type of set of string
  labels = []
  # listen_ipv4_uuid - (required) is a type of string
  listen_ipv4_uuid = null
  # listen_ipv6_uuid - (required) is a type of string
  listen_ipv6_uuid = null
  # name - (required) is a type of string
  name = null
  # redirect_http_to_https - (required) is a type of bool
  redirect_http_to_https = null
  # status - (optional) is a type of string
  status = null

  backend_server = [{
    host   = null
    weight = null
  }]

  forwarding_rule = [{
    letsencrypt_ssl = null
    listen_port     = null
    mode            = null
    target_port     = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "algorithm" {
  description = "(required) - The algorithm used to process requests. Accepted values: roundrobin/leastconn."
  type        = string
}

variable "labels" {
  description = "(optional) - List of labels."
  type        = set(string)
  default     = null
}

variable "listen_ipv4_uuid" {
  description = "(required) - The UUID of the IPv4 address the Load balancer will listen to for incoming requests."
  type        = string
}

variable "listen_ipv6_uuid" {
  description = "(required) - The UUID of the IPv6 address the Load balancer will listen to for incoming requests."
  type        = string
}

variable "name" {
  description = "(required) - The human-readable name of the object. It supports the full UTF-8 character set, with a maximum of 64 characters"
  type        = string
}

variable "redirect_http_to_https" {
  description = "(required) - Whether the Load balancer is forced to redirect requests from HTTP to HTTPS"
  type        = bool
}

variable "status" {
  description = "(optional) - Status indicates the status of the object."
  type        = string
  default     = null
}

variable "backend_server" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      host   = string
      weight = number
    }
  ))
}

variable "forwarding_rule" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      letsencrypt_ssl = string
      listen_port     = number
      mode            = string
      target_port     = number
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "gridscale_loadbalancer" "this" {
  algorithm              = var.algorithm
  labels                 = var.labels
  listen_ipv4_uuid       = var.listen_ipv4_uuid
  listen_ipv6_uuid       = var.listen_ipv6_uuid
  name                   = var.name
  redirect_http_to_https = var.redirect_http_to_https
  status                 = var.status

  dynamic "backend_server" {
    for_each = var.backend_server
    content {
      host   = backend_server.value["host"]
      weight = backend_server.value["weight"]
    }
  }

  dynamic "forwarding_rule" {
    for_each = var.forwarding_rule
    content {
      letsencrypt_ssl = forwarding_rule.value["letsencrypt_ssl"]
      listen_port     = forwarding_rule.value["listen_port"]
      mode            = forwarding_rule.value["mode"]
      target_port     = forwarding_rule.value["target_port"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gridscale_loadbalancer.this.id
}

output "location_uuid" {
  description = "returns a string"
  value       = gridscale_loadbalancer.this.location_uuid
}

output "this" {
  value = gridscale_loadbalancer.this
}
```

[top](#index)