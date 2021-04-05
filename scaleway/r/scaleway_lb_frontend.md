# scaleway_lb_frontend

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_lb_frontend" {
  source = "./modules/scaleway/r/scaleway_lb_frontend"

  # backend_id - (required) is a type of string
  backend_id = null
  # certificate_id - (optional) is a type of string
  certificate_id = null
  # inbound_port - (required) is a type of number
  inbound_port = null
  # lb_id - (required) is a type of string
  lb_id = null
  # name - (optional) is a type of string
  name = null
  # timeout_client - (optional) is a type of string
  timeout_client = null

  acl = [{
    action = [{
      type = null
    }]
    match = [{
      http_filter       = null
      http_filter_value = []
      invert            = null
      ip_subnet         = []
    }]
    name            = null
    organization_id = null
    region          = null
  }]

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "backend_id" {
  description = "(required) - The load-balancer backend ID"
  type        = string
}

variable "certificate_id" {
  description = "(optional) - Certificate ID"
  type        = string
  default     = null
}

variable "inbound_port" {
  description = "(required) - TCP port to listen on the front side"
  type        = number
}

variable "lb_id" {
  description = "(required) - The load-balancer ID"
  type        = string
}

variable "name" {
  description = "(optional) - The name of the frontend"
  type        = string
  default     = null
}

variable "timeout_client" {
  description = "(optional) - Set the maximum inactivity time on the client side"
  type        = string
  default     = null
}

variable "acl" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = list(object(
        {
          type = string
        }
      ))
      match = list(object(
        {
          http_filter       = string
          http_filter_value = list(string)
          invert            = bool
          ip_subnet         = list(string)
        }
      ))
      name            = string
      organization_id = string
      region          = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_lb_frontend" "this" {
  backend_id     = var.backend_id
  certificate_id = var.certificate_id
  inbound_port   = var.inbound_port
  lb_id          = var.lb_id
  name           = var.name
  timeout_client = var.timeout_client

  dynamic "acl" {
    for_each = var.acl
    content {
      name   = acl.value["name"]
      region = acl.value["region"]

      dynamic "action" {
        for_each = acl.value.action
        content {
          type = action.value["type"]
        }
      }

      dynamic "match" {
        for_each = acl.value.match
        content {
          http_filter       = match.value["http_filter"]
          http_filter_value = match.value["http_filter_value"]
          invert            = match.value["invert"]
          ip_subnet         = match.value["ip_subnet"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = scaleway_lb_frontend.this.id
}

output "name" {
  description = "returns a string"
  value       = scaleway_lb_frontend.this.name
}

output "this" {
  value = scaleway_lb_frontend.this
}
```

[top](#index)