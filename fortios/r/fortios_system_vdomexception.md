# fortios_system_vdomexception

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_vdomexception" {
  source = "./modules/fortios/r/fortios_system_vdomexception"

  # fosid - (optional) is a type of number
  fosid = null
  # object - (required) is a type of string
  object = null
  # oid - (optional) is a type of number
  oid = null
  # scope - (optional) is a type of string
  scope = null

  vdom = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "object" {
  description = "(required)"
  type        = string
}

variable "oid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vdom" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_vdomexception" "this" {
  fosid  = var.fosid
  object = var.object
  oid    = var.oid
  scope  = var.scope

  dynamic "vdom" {
    for_each = var.vdom
    content {
      name = vdom.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_system_vdomexception.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_system_vdomexception.this.id
}

output "oid" {
  description = "returns a number"
  value       = fortios_system_vdomexception.this.oid
}

output "scope" {
  description = "returns a string"
  value       = fortios_system_vdomexception.this.scope
}

output "this" {
  value = fortios_system_vdomexception.this
}
```

[top](#index)