# brightbox_load_balancer

[back](../brightbox.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    brightbox = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "brightbox_load_balancer" {
  source = "./modules/brightbox/r/brightbox_load_balancer"

  # buffer_size - (optional) is a type of number
  buffer_size = null
  # certificate_pem - (optional) is a type of string
  certificate_pem = null
  # certificate_private_key - (optional) is a type of string
  certificate_private_key = null
  # domains - (optional) is a type of set of string
  domains = []
  # https_redirect - (optional) is a type of bool
  https_redirect = null
  # locked - (optional) is a type of bool
  locked = null
  # name - (optional) is a type of string
  name = null
  # nodes - (optional) is a type of set of string
  nodes = []
  # policy - (optional) is a type of string
  policy = null
  # ssl_minimum_version - (optional) is a type of string
  ssl_minimum_version = null
  # sslv3 - (optional) is a type of bool
  sslv3 = null

  healthcheck = [{
    interval       = null
    port           = null
    request        = null
    threshold_down = null
    threshold_up   = null
    timeout        = null
    type           = null
  }]

  listener = [{
    in             = null
    out            = null
    protocol       = null
    proxy_protocol = null
    timeout        = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "buffer_size" {
  description = "(optional) - Buffer size in bytes"
  type        = number
  default     = null
}

variable "certificate_pem" {
  description = "(optional) - A X509 SSL certificate in PEM format"
  type        = string
  default     = null
}

variable "certificate_private_key" {
  description = "(optional) - RSA private key used to sign the certificate in PEM format"
  type        = string
  default     = null
}

variable "domains" {
  description = "(optional) - Array of domain names to attempt to register with ACME"
  type        = set(string)
  default     = null
}

variable "https_redirect" {
  description = "(optional) - Redirect any requests on port 80 automatically to port 443"
  type        = bool
  default     = null
}

variable "locked" {
  description = "(optional) - Is true if resource has been set as locked and can not be deleted"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - Editable user label"
  type        = string
  default     = null
}

variable "nodes" {
  description = "(optional) - IDs of servers connected to this load balancer"
  type        = set(string)
  default     = null
}

variable "policy" {
  description = "(optional) - Method of load balancing. Supports `least-connections`, `round-robin` or `source-address`)"
  type        = string
  default     = null
}

variable "ssl_minimum_version" {
  description = "(optional) - The minimum TLS/SSL version for the load balancer to accept. Supports `TLSv1.0`, `TLSv1.1`, `TLSv1.2`, `TLSv1.3` and `SSLv3`"
  type        = string
  default     = null
}

variable "sslv3" {
  description = "(optional) - Allow SSLv3 to be used"
  type        = bool
  default     = null
}

variable "healthcheck" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      interval       = number
      port           = number
      request        = string
      threshold_down = number
      threshold_up   = number
      timeout        = number
      type           = string
    }
  ))
}

variable "listener" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      in             = number
      out            = number
      protocol       = string
      proxy_protocol = string
      timeout        = number
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "brightbox_load_balancer" "this" {
  buffer_size             = var.buffer_size
  certificate_pem         = var.certificate_pem
  certificate_private_key = var.certificate_private_key
  domains                 = var.domains
  https_redirect          = var.https_redirect
  locked                  = var.locked
  name                    = var.name
  nodes                   = var.nodes
  policy                  = var.policy
  ssl_minimum_version     = var.ssl_minimum_version
  sslv3                   = var.sslv3

  dynamic "healthcheck" {
    for_each = var.healthcheck
    content {
      interval       = healthcheck.value["interval"]
      port           = healthcheck.value["port"]
      request        = healthcheck.value["request"]
      threshold_down = healthcheck.value["threshold_down"]
      threshold_up   = healthcheck.value["threshold_up"]
      timeout        = healthcheck.value["timeout"]
      type           = healthcheck.value["type"]
    }
  }

  dynamic "listener" {
    for_each = var.listener
    content {
      in             = listener.value["in"]
      out            = listener.value["out"]
      protocol       = listener.value["protocol"]
      proxy_protocol = listener.value["proxy_protocol"]
      timeout        = listener.value["timeout"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "buffer_size" {
  description = "returns a number"
  value       = brightbox_load_balancer.this.buffer_size
}

output "id" {
  description = "returns a string"
  value       = brightbox_load_balancer.this.id
}

output "nodes" {
  description = "returns a set of string"
  value       = brightbox_load_balancer.this.nodes
}

output "policy" {
  description = "returns a string"
  value       = brightbox_load_balancer.this.policy
}

output "ssl_minimum_version" {
  description = "returns a string"
  value       = brightbox_load_balancer.this.ssl_minimum_version
}

output "status" {
  description = "returns a string"
  value       = brightbox_load_balancer.this.status
}

output "this" {
  value = brightbox_load_balancer.this
}
```

[top](#index)