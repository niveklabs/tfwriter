# oraclepaas_mysql_access_rule

[back](../oraclepaas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oraclepaas = ">= 1.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oraclepaas_mysql_access_rule" {
  source = null

  # description - (optional) is a type of string
  description = null
  # destination - (required) is a type of string
  destination = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # ports - (required) is a type of string
  ports = null
  # protocol - (optional) is a type of string
  protocol = null
  # service_instance_id - (required) is a type of string
  service_instance_id = null
  # source - (required) is a type of string

  timeouts = [{
    create = null
    delete = null
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

variable "destination" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "ports" {
  description = "(required)"
  type        = string
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_instance_id" {
  description = "(required)"
  type        = string
}

variable "source" {
  description = "(required)"
  type        = string
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
resource "oraclepaas_mysql_access_rule" "this" {
  # description - (optional) is a type of string
  description = var.description
  # destination - (required) is a type of string
  destination = var.destination
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # ports - (required) is a type of string
  ports = var.ports
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # service_instance_id - (required) is a type of string
  service_instance_id = var.service_instance_id
  # source - (required) is a type of string
  source = var.source

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = oraclepaas_mysql_access_rule.this.id
}

output "type" {
  description = "returns a string"
  value       = oraclepaas_mysql_access_rule.this.type
}

output "this" {
  value = oraclepaas_mysql_access_rule.this
}
```

[top](#index)