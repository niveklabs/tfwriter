# gridscale_paas

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
    gridscale = ">= 1.8.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_paas" {
  source = "./modules/gridscale/r/gridscale_paas"

  # labels - (optional) is a type of set of string
  labels = []
  # name - (required) is a type of string
  name = null
  # security_zone_uuid - (optional) is a type of string
  security_zone_uuid = null
  # service_template_uuid - (required) is a type of string
  service_template_uuid = null

  parameter = [{
    param = null
    type  = null
    value = null
  }]

  resource_limit = [{
    limit    = null
    resource = null
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
variable "labels" {
  description = "(optional) - List of labels."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - The human-readable name of the object. It supports the full UTF-8 character set, with a maximum of 64 characters"
  type        = string
}

variable "security_zone_uuid" {
  description = "(optional) - Security zone UUID linked to PaaS service"
  type        = string
  default     = null
}

variable "service_template_uuid" {
  description = "(required) - Template that PaaS service uses"
  type        = string
}

variable "parameter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      param = string
      type  = string
      value = string
    }
  ))
  default = []
}

variable "resource_limit" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      limit    = number
      resource = string
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
resource "gridscale_paas" "this" {
  # labels - (optional) is a type of set of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # security_zone_uuid - (optional) is a type of string
  security_zone_uuid = var.security_zone_uuid
  # service_template_uuid - (required) is a type of string
  service_template_uuid = var.service_template_uuid

  dynamic "parameter" {
    for_each = var.parameter
    content {
      # param - (required) is a type of string
      param = parameter.value["param"]
      # type - (required) is a type of string
      type = parameter.value["type"]
      # value - (required) is a type of string
      value = parameter.value["value"]
    }
  }

  dynamic "resource_limit" {
    for_each = var.resource_limit
    content {
      # limit - (required) is a type of number
      limit = resource_limit.value["limit"]
      # resource - (required) is a type of string
      resource = resource_limit.value["resource"]
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
output "change_time" {
  description = "returns a string"
  value       = gridscale_paas.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_paas.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = gridscale_paas.this.current_price
}

output "id" {
  description = "returns a string"
  value       = gridscale_paas.this.id
}

output "kubeconfig" {
  description = "returns a string"
  value       = gridscale_paas.this.kubeconfig
}

output "listen_port" {
  description = "returns a set of object"
  value       = gridscale_paas.this.listen_port
}

output "network_uuid" {
  description = "returns a string"
  value       = gridscale_paas.this.network_uuid
}

output "password" {
  description = "returns a string"
  value       = gridscale_paas.this.password
}

output "security_zone_uuid" {
  description = "returns a string"
  value       = gridscale_paas.this.security_zone_uuid
}

output "service_template_uuid_computed" {
  description = "returns a string"
  value       = gridscale_paas.this.service_template_uuid_computed
}

output "status" {
  description = "returns a string"
  value       = gridscale_paas.this.status
}

output "usage_in_minute" {
  description = "returns a number"
  value       = gridscale_paas.this.usage_in_minute
}

output "username" {
  description = "returns a string"
  value       = gridscale_paas.this.username
}

output "this" {
  value = gridscale_paas.this
}
```

[top](#index)