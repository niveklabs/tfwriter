# skytap_environment

[back](../skytap.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    skytap = ">= 0.14.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "skytap_environment" {
  source = "./modules/skytap/r/skytap_environment"

  # description - (required) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # outbound_traffic - (optional) is a type of bool
  outbound_traffic = null
  # routable - (optional) is a type of bool
  routable = null
  # shutdown_at_time - (optional) is a type of string
  shutdown_at_time = null
  # shutdown_on_idle - (optional) is a type of number
  shutdown_on_idle = null
  # suspend_at_time - (optional) is a type of string
  suspend_at_time = null
  # suspend_on_idle - (optional) is a type of number
  suspend_on_idle = null
  # tags - (optional) is a type of set of string
  tags = []
  # template_id - (required) is a type of string
  template_id = null
  # user_data - (optional) is a type of string
  user_data = null

  label = [{
    category = null
    id       = null
    value    = null
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
variable "description" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "outbound_traffic" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "routable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "shutdown_at_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shutdown_on_idle" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "suspend_at_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "suspend_on_idle" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "template_id" {
  description = "(required)"
  type        = string
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "label" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      category = string
      id       = string
      value    = string
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
resource "skytap_environment" "this" {
  # description - (required) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # outbound_traffic - (optional) is a type of bool
  outbound_traffic = var.outbound_traffic
  # routable - (optional) is a type of bool
  routable = var.routable
  # shutdown_at_time - (optional) is a type of string
  shutdown_at_time = var.shutdown_at_time
  # shutdown_on_idle - (optional) is a type of number
  shutdown_on_idle = var.shutdown_on_idle
  # suspend_at_time - (optional) is a type of string
  suspend_at_time = var.suspend_at_time
  # suspend_on_idle - (optional) is a type of number
  suspend_on_idle = var.suspend_on_idle
  # tags - (optional) is a type of set of string
  tags = var.tags
  # template_id - (required) is a type of string
  template_id = var.template_id
  # user_data - (optional) is a type of string
  user_data = var.user_data

  dynamic "label" {
    for_each = var.label
    content {
      # category - (required) is a type of string
      category = label.value["category"]
      # value - (required) is a type of string
      value = label.value["value"]
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
output "id" {
  description = "returns a string"
  value       = skytap_environment.this.id
}

output "this" {
  value = skytap_environment.this
}
```

[top](#index)