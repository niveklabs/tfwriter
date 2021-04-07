# consul_service

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    consul = ">= 2.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_service" {
  source = "./modules/consul/r/consul_service"

  # address - (optional) is a type of string
  address = null
  # datacenter - (optional) is a type of string
  datacenter = null
  # enable_tag_override - (optional) is a type of bool
  enable_tag_override = null
  # external - (optional) is a type of bool
  external = null
  # meta - (optional) is a type of map of string
  meta = {}
  # name - (required) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
  # node - (required) is a type of string
  node = null
  # port - (optional) is a type of number
  port = null
  # service_id - (optional) is a type of string
  service_id = null
  # tags - (optional) is a type of list of string
  tags = []

  check = [{
    check_id                          = null
    deregister_critical_service_after = null
    header = [{
      name  = null
      value = []
    }]
    http            = null
    interval        = null
    method          = null
    name            = null
    notes           = null
    status          = null
    tcp             = null
    timeout         = null
    tls_skip_verify = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "datacenter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_tag_override" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "external" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "meta" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "check" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      check_id                          = string
      deregister_critical_service_after = string
      header = set(object(
        {
          name  = string
          value = list(string)
        }
      ))
      http            = string
      interval        = string
      method          = string
      name            = string
      notes           = string
      status          = string
      tcp             = string
      timeout         = string
      tls_skip_verify = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "consul_service" "this" {
  # address - (optional) is a type of string
  address = var.address
  # datacenter - (optional) is a type of string
  datacenter = var.datacenter
  # enable_tag_override - (optional) is a type of bool
  enable_tag_override = var.enable_tag_override
  # external - (optional) is a type of bool
  external = var.external
  # meta - (optional) is a type of map of string
  meta = var.meta
  # name - (required) is a type of string
  name = var.name
  # namespace - (optional) is a type of string
  namespace = var.namespace
  # node - (required) is a type of string
  node = var.node
  # port - (optional) is a type of number
  port = var.port
  # service_id - (optional) is a type of string
  service_id = var.service_id
  # tags - (optional) is a type of list of string
  tags = var.tags

  dynamic "check" {
    for_each = var.check
    content {
      # check_id - (required) is a type of string
      check_id = check.value["check_id"]
      # deregister_critical_service_after - (optional) is a type of string
      deregister_critical_service_after = check.value["deregister_critical_service_after"]
      # http - (optional) is a type of string
      http = check.value["http"]
      # interval - (required) is a type of string
      interval = check.value["interval"]
      # method - (optional) is a type of string
      method = check.value["method"]
      # name - (required) is a type of string
      name = check.value["name"]
      # notes - (optional) is a type of string
      notes = check.value["notes"]
      # status - (optional) is a type of string
      status = check.value["status"]
      # tcp - (optional) is a type of string
      tcp = check.value["tcp"]
      # timeout - (required) is a type of string
      timeout = check.value["timeout"]
      # tls_skip_verify - (optional) is a type of bool
      tls_skip_verify = check.value["tls_skip_verify"]

      dynamic "header" {
        for_each = check.value.header
        content {
          # name - (required) is a type of string
          name = header.value["name"]
          # value - (required) is a type of list of string
          value = header.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = consul_service.this.address
}

output "datacenter" {
  description = "returns a string"
  value       = consul_service.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = consul_service.this.id
}

output "service_id" {
  description = "returns a string"
  value       = consul_service.this.service_id
}

output "this" {
  value = consul_service.this
}
```

[top](#index)