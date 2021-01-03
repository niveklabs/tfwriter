# oci_load_balancer_listener

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_load_balancer_listener" {
  source = "./modules/oci/r/oci_load_balancer_listener"

  # default_backend_set_name - (required) is a type of string
  default_backend_set_name = null
  # hostname_names - (optional) is a type of list of string
  hostname_names = []
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # name - (required) is a type of string
  name = null
  # path_route_set_name - (optional) is a type of string
  path_route_set_name = null
  # port - (required) is a type of number
  port = null
  # protocol - (required) is a type of string
  protocol = null
  # rule_set_names - (optional) is a type of list of string
  rule_set_names = []

  connection_configuration = [{
    backend_tcp_proxy_protocol_version = null
    idle_timeout_in_seconds            = null
  }]

  ssl_configuration = [{
    certificate_name        = null
    cipher_suite_name       = null
    protocols               = []
    server_order_preference = null
    verify_depth            = null
    verify_peer_certificate = null
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
variable "default_backend_set_name" {
  description = "(required)"
  type        = string
}

variable "hostname_names" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "path_route_set_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "rule_set_names" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "connection_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      backend_tcp_proxy_protocol_version = number
      idle_timeout_in_seconds            = string
    }
  ))
  default = []
}

variable "ssl_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      certificate_name        = string
      cipher_suite_name       = string
      protocols               = list(string)
      server_order_preference = string
      verify_depth            = number
      verify_peer_certificate = bool
    }
  ))
  default = []
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
resource "oci_load_balancer_listener" "this" {
  default_backend_set_name = var.default_backend_set_name
  hostname_names           = var.hostname_names
  load_balancer_id         = var.load_balancer_id
  name                     = var.name
  path_route_set_name      = var.path_route_set_name
  port                     = var.port
  protocol                 = var.protocol
  rule_set_names           = var.rule_set_names

  dynamic "connection_configuration" {
    for_each = var.connection_configuration
    content {
      backend_tcp_proxy_protocol_version = connection_configuration.value["backend_tcp_proxy_protocol_version"]
      idle_timeout_in_seconds            = connection_configuration.value["idle_timeout_in_seconds"]
    }
  }

  dynamic "ssl_configuration" {
    for_each = var.ssl_configuration
    content {
      certificate_name        = ssl_configuration.value["certificate_name"]
      cipher_suite_name       = ssl_configuration.value["cipher_suite_name"]
      protocols               = ssl_configuration.value["protocols"]
      server_order_preference = ssl_configuration.value["server_order_preference"]
      verify_depth            = ssl_configuration.value["verify_depth"]
      verify_peer_certificate = ssl_configuration.value["verify_peer_certificate"]
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
output "hostname_names" {
  description = "returns a list of string"
  value       = oci_load_balancer_listener.this.hostname_names
}

output "id" {
  description = "returns a string"
  value       = oci_load_balancer_listener.this.id
}

output "path_route_set_name" {
  description = "returns a string"
  value       = oci_load_balancer_listener.this.path_route_set_name
}

output "rule_set_names" {
  description = "returns a list of string"
  value       = oci_load_balancer_listener.this.rule_set_names
}

output "state" {
  description = "returns a string"
  value       = oci_load_balancer_listener.this.state
}

output "this" {
  value = oci_load_balancer_listener.this
}
```

[top](#index)