# turbot_mod

[back](../turbot.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    turbot = ">= 1.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "turbot_mod" {
  source = "./modules/turbot/r/turbot_mod"

  # mod - (required) is a type of string
  mod = null
  # org - (required) is a type of string
  org = null
  # parent - (optional) is a type of string
  parent = null
  # version - (optional) is a type of string
  version = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "mod" {
  description = "(required)"
  type        = string
}

variable "org" {
  description = "(required)"
  type        = string
}

variable "parent" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "turbot_mod" "this" {
  # mod - (required) is a type of string
  mod = var.mod
  # org - (required) is a type of string
  org = var.org
  # parent - (optional) is a type of string
  parent = var.parent
  # version - (optional) is a type of string
  version = var.version

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = turbot_mod.this.id
}

output "parent_akas" {
  description = "returns a list of string"
  value       = turbot_mod.this.parent_akas
}

output "uri" {
  description = "returns a string"
  value       = turbot_mod.this.uri
}

output "version_current" {
  description = "returns a string"
  value       = turbot_mod.this.version_current
}

output "version_latest" {
  description = "returns a string"
  value       = turbot_mod.this.version_latest
}

output "this" {
  value = turbot_mod.this
}
```

[top](#index)