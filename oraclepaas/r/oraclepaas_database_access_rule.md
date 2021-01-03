# oraclepaas_database_access_rule

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
module "oraclepaas_database_access_rule" {
  source = null

  # description - (required) is a type of string
  description = null
  # destination - (optional) is a type of string
  destination = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # ports - (required) is a type of string
  ports = null
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
  description = "(required)"
  type        = string
}

variable "destination" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "oraclepaas_database_access_rule" "this" {
  description         = var.description
  destination         = var.destination
  enabled             = var.enabled
  name                = var.name
  ports               = var.ports
  service_instance_id = var.service_instance_id
  source              = var.source

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
output "id" {
  description = "returns a string"
  value       = oraclepaas_database_access_rule.this.id
}

output "this" {
  value = oraclepaas_database_access_rule.this
}
```

[top](#index)