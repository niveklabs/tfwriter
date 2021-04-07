# oci_network_load_balancer_backend_set

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
module "oci_network_load_balancer_backend_set" {
  source = "./modules/oci/r/oci_network_load_balancer_backend_set"

  # is_preserve_source - (optional) is a type of bool
  is_preserve_source = null
  # name - (required) is a type of string
  name = null
  # network_load_balancer_id - (required) is a type of string
  network_load_balancer_id = null
  # policy - (required) is a type of string
  policy = null

  health_checker = [{
    interval_in_millis  = null
    port                = null
    protocol            = null
    request_data        = null
    response_body_regex = null
    response_data       = null
    retries             = null
    return_code         = null
    timeout_in_millis   = null
    url_path            = null
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
variable "is_preserve_source" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_load_balancer_id" {
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
      interval_in_millis  = number
      port                = number
      protocol            = string
      request_data        = string
      response_body_regex = string
      response_data       = string
      retries             = number
      return_code         = number
      timeout_in_millis   = number
      url_path            = string
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
resource "oci_network_load_balancer_backend_set" "this" {
  # is_preserve_source - (optional) is a type of bool
  is_preserve_source = var.is_preserve_source
  # name - (required) is a type of string
  name = var.name
  # network_load_balancer_id - (required) is a type of string
  network_load_balancer_id = var.network_load_balancer_id
  # policy - (required) is a type of string
  policy = var.policy

  dynamic "health_checker" {
    for_each = var.health_checker
    content {
      # interval_in_millis - (optional) is a type of number
      interval_in_millis = health_checker.value["interval_in_millis"]
      # port - (optional) is a type of number
      port = health_checker.value["port"]
      # protocol - (required) is a type of string
      protocol = health_checker.value["protocol"]
      # request_data - (optional) is a type of string
      request_data = health_checker.value["request_data"]
      # response_body_regex - (optional) is a type of string
      response_body_regex = health_checker.value["response_body_regex"]
      # response_data - (optional) is a type of string
      response_data = health_checker.value["response_data"]
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
output "backends" {
  description = "returns a list of object"
  value       = oci_network_load_balancer_backend_set.this.backends
}

output "id" {
  description = "returns a string"
  value       = oci_network_load_balancer_backend_set.this.id
}

output "is_preserve_source" {
  description = "returns a bool"
  value       = oci_network_load_balancer_backend_set.this.is_preserve_source
}

output "this" {
  value = oci_network_load_balancer_backend_set.this
}
```

[top](#index)