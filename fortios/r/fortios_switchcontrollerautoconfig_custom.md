# fortios_switchcontrollerautoconfig_custom

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_switchcontrollerautoconfig_custom" {
  source = "./modules/fortios/r/fortios_switchcontrollerautoconfig_custom"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (required) is a type of string
  name = null

  switch_binding = [{
    policy    = null
    switch_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "switch_binding" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      policy    = string
      switch_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollerautoconfig_custom" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  name                  = var.name

  dynamic "switch_binding" {
    for_each = var.switch_binding
    content {
      policy    = switch_binding.value["policy"]
      switch_id = switch_binding.value["switch_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_custom.this.id
}

output "this" {
  value = fortios_switchcontrollerautoconfig_custom.this
}
```

[top](#index)