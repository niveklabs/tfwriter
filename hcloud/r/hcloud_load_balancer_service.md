# hcloud_load_balancer_service

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
module "hcloud_load_balancer_service" {
  source = "./modules/hcloud/r/hcloud_load_balancer_service"

  # destination_port - (optional) is a type of number
  destination_port = null
  # listen_port - (optional) is a type of number
  listen_port = null
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # protocol - (required) is a type of string
  protocol = null
  # proxyprotocol - (optional) is a type of bool
  proxyprotocol = null

  health_check = [{
    http = [{
      domain       = null
      path         = null
      response     = null
      status_codes = []
      tls          = null
    }]
    interval = null
    port     = null
    protocol = null
    retries  = null
    timeout  = null
  }]

  http = [{
    certificates    = []
    cookie_lifetime = null
    cookie_name     = null
    redirect_http   = null
    sticky_sessions = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "destination_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "listen_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "proxyprotocol" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "health_check" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      http = list(object(
        {
          domain       = string
          path         = string
          response     = string
          status_codes = list(string)
          tls          = bool
        }
      ))
      interval = number
      port     = number
      protocol = string
      retries  = number
      timeout  = number
    }
  ))
  default = []
}

variable "http" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      certificates    = set(number)
      cookie_lifetime = number
      cookie_name     = string
      redirect_http   = bool
      sticky_sessions = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_load_balancer_service" "this" {
  # destination_port - (optional) is a type of number
  destination_port = var.destination_port
  # listen_port - (optional) is a type of number
  listen_port = var.listen_port
  # load_balancer_id - (required) is a type of string
  load_balancer_id = var.load_balancer_id
  # protocol - (required) is a type of string
  protocol = var.protocol
  # proxyprotocol - (optional) is a type of bool
  proxyprotocol = var.proxyprotocol

  dynamic "health_check" {
    for_each = var.health_check
    content {
      # interval - (required) is a type of number
      interval = health_check.value["interval"]
      # port - (required) is a type of number
      port = health_check.value["port"]
      # protocol - (required) is a type of string
      protocol = health_check.value["protocol"]
      # retries - (optional) is a type of number
      retries = health_check.value["retries"]
      # timeout - (required) is a type of number
      timeout = health_check.value["timeout"]

      dynamic "http" {
        for_each = health_check.value.http
        content {
          # domain - (optional) is a type of string
          domain = http.value["domain"]
          # path - (optional) is a type of string
          path = http.value["path"]
          # response - (optional) is a type of string
          response = http.value["response"]
          # status_codes - (optional) is a type of list of string
          status_codes = http.value["status_codes"]
          # tls - (optional) is a type of bool
          tls = http.value["tls"]
        }
      }

    }
  }

  dynamic "http" {
    for_each = var.http
    content {
      # certificates - (optional) is a type of set of number
      certificates = http.value["certificates"]
      # cookie_lifetime - (optional) is a type of number
      cookie_lifetime = http.value["cookie_lifetime"]
      # cookie_name - (optional) is a type of string
      cookie_name = http.value["cookie_name"]
      # redirect_http - (optional) is a type of bool
      redirect_http = http.value["redirect_http"]
      # sticky_sessions - (optional) is a type of bool
      sticky_sessions = http.value["sticky_sessions"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "destination_port" {
  description = "returns a number"
  value       = hcloud_load_balancer_service.this.destination_port
}

output "id" {
  description = "returns a string"
  value       = hcloud_load_balancer_service.this.id
}

output "listen_port" {
  description = "returns a number"
  value       = hcloud_load_balancer_service.this.listen_port
}

output "proxyprotocol" {
  description = "returns a bool"
  value       = hcloud_load_balancer_service.this.proxyprotocol
}

output "this" {
  value = hcloud_load_balancer_service.this
}
```

[top](#index)