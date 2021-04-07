# oci_load_balancer_backendset

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_load_balancer_backendset" {
  source = "./modules/oci/r/oci_load_balancer_backendset"

  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # name - (required) is a type of string
  name = null
  # policy - (required) is a type of string
  policy = null

  health_checker = [{
    interval_ms         = null
    port                = null
    protocol            = null
    response_body_regex = null
    retries             = null
    return_code         = null
    timeout_in_millis   = null
    url_path            = null
  }]

  lb_cookie_session_persistence_configuration = [{
    cookie_name        = null
    disable_fallback   = null
    domain             = null
    is_http_only       = null
    is_secure          = null
    max_age_in_seconds = null
    path               = null
  }]

  session_persistence_configuration = [{
    cookie_name      = null
    disable_fallback = null
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
variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "policy" {
  description = "(required)"
  type        = string
}

variable "health_checker" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      interval_ms         = number
      port                = number
      protocol            = string
      response_body_regex = string
      retries             = number
      return_code         = number
      timeout_in_millis   = number
      url_path            = string
    }
  ))
}

variable "lb_cookie_session_persistence_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cookie_name        = string
      disable_fallback   = bool
      domain             = string
      is_http_only       = bool
      is_secure          = bool
      max_age_in_seconds = number
      path               = string
    }
  ))
  default = []
}

variable "session_persistence_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cookie_name      = string
      disable_fallback = bool
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
resource "oci_load_balancer_backendset" "this" {
  # load_balancer_id - (required) is a type of string
  load_balancer_id = var.load_balancer_id
  # name - (required) is a type of string
  name = var.name
  # policy - (required) is a type of string
  policy = var.policy

  dynamic "health_checker" {
    for_each = var.health_checker
    content {
      # interval_ms - (optional) is a type of number
      interval_ms = health_checker.value["interval_ms"]
      # port - (optional) is a type of number
      port = health_checker.value["port"]
      # protocol - (required) is a type of string
      protocol = health_checker.value["protocol"]
      # response_body_regex - (optional) is a type of string
      response_body_regex = health_checker.value["response_body_regex"]
      # retries - (optional) is a type of number
      retries = health_checker.value["retries"]
      # return_code - (optional) is a type of number
      return_code = health_checker.value["return_code"]
      # timeout_in_millis - (optional) is a type of number
      timeout_in_millis = health_checker.value["timeout_in_millis"]
      # url_path - (optional) is a type of string
      url_path = health_checker.value["url_path"]
    }
  }

  dynamic "lb_cookie_session_persistence_configuration" {
    for_each = var.lb_cookie_session_persistence_configuration
    content {
      # cookie_name - (optional) is a type of string
      cookie_name = lb_cookie_session_persistence_configuration.value["cookie_name"]
      # disable_fallback - (optional) is a type of bool
      disable_fallback = lb_cookie_session_persistence_configuration.value["disable_fallback"]
      # domain - (optional) is a type of string
      domain = lb_cookie_session_persistence_configuration.value["domain"]
      # is_http_only - (optional) is a type of bool
      is_http_only = lb_cookie_session_persistence_configuration.value["is_http_only"]
      # is_secure - (optional) is a type of bool
      is_secure = lb_cookie_session_persistence_configuration.value["is_secure"]
      # max_age_in_seconds - (optional) is a type of number
      max_age_in_seconds = lb_cookie_session_persistence_configuration.value["max_age_in_seconds"]
      # path - (optional) is a type of string
      path = lb_cookie_session_persistence_configuration.value["path"]
    }
  }

  dynamic "session_persistence_configuration" {
    for_each = var.session_persistence_configuration
    content {
      # cookie_name - (required) is a type of string
      cookie_name = session_persistence_configuration.value["cookie_name"]
      # disable_fallback - (optional) is a type of bool
      disable_fallback = session_persistence_configuration.value["disable_fallback"]
    }
  }

  dynamic "ssl_configuration" {
    for_each = var.ssl_configuration
    content {
      # certificate_name - (required) is a type of string
      certificate_name = ssl_configuration.value["certificate_name"]
      # cipher_suite_name - (optional) is a type of string
      cipher_suite_name = ssl_configuration.value["cipher_suite_name"]
      # protocols - (optional) is a type of list of string
      protocols = ssl_configuration.value["protocols"]
      # server_order_preference - (optional) is a type of string
      server_order_preference = ssl_configuration.value["server_order_preference"]
      # verify_depth - (optional) is a type of number
      verify_depth = ssl_configuration.value["verify_depth"]
      # verify_peer_certificate - (optional) is a type of bool
      verify_peer_certificate = ssl_configuration.value["verify_peer_certificate"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "backend" {
  description = "returns a set of object"
  value       = oci_load_balancer_backendset.this.backend
}

output "id" {
  description = "returns a string"
  value       = oci_load_balancer_backendset.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_load_balancer_backendset.this.state
}

output "this" {
  value = oci_load_balancer_backendset.this
}
```

[top](#index)