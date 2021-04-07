# exoscale_nlb_service

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_nlb_service" {
  source = "./modules/exoscale/r/exoscale_nlb_service"

  # description - (optional) is a type of string
  description = null
  # instance_pool_id - (required) is a type of string
  instance_pool_id = null
  # name - (required) is a type of string
  name = null
  # nlb_id - (required) is a type of string
  nlb_id = null
  # port - (required) is a type of number
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # strategy - (optional) is a type of string
  strategy = null
  # target_port - (required) is a type of number
  target_port = null
  # zone - (required) is a type of string
  zone = null

  healthcheck = [{
    interval = null
    mode     = null
    port     = null
    retries  = null
    timeout  = null
    tls_sni  = null
    uri      = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_pool_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "nlb_id" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_port" {
  description = "(required)"
  type        = number
}

variable "zone" {
  description = "(required)"
  type        = string
}

variable "healthcheck" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      interval = number
      mode     = string
      port     = number
      retries  = number
      timeout  = number
      tls_sni  = string
      uri      = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "exoscale_nlb_service" "this" {
  # description - (optional) is a type of string
  description = var.description
  # instance_pool_id - (required) is a type of string
  instance_pool_id = var.instance_pool_id
  # name - (required) is a type of string
  name = var.name
  # nlb_id - (required) is a type of string
  nlb_id = var.nlb_id
  # port - (required) is a type of number
  port = var.port
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # strategy - (optional) is a type of string
  strategy = var.strategy
  # target_port - (required) is a type of number
  target_port = var.target_port
  # zone - (required) is a type of string
  zone = var.zone

  dynamic "healthcheck" {
    for_each = var.healthcheck
    content {
      # interval - (optional) is a type of number
      interval = healthcheck.value["interval"]
      # mode - (optional) is a type of string
      mode = healthcheck.value["mode"]
      # port - (required) is a type of number
      port = healthcheck.value["port"]
      # retries - (optional) is a type of number
      retries = healthcheck.value["retries"]
      # timeout - (optional) is a type of number
      timeout = healthcheck.value["timeout"]
      # tls_sni - (optional) is a type of string
      tls_sni = healthcheck.value["tls_sni"]
      # uri - (optional) is a type of string
      uri = healthcheck.value["uri"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
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
  value       = exoscale_nlb_service.this.id
}

output "this" {
  value = exoscale_nlb_service.this
}
```

[top](#index)