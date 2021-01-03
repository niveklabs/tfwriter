# fortios_system_ssoadmin

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
module "fortios_system_ssoadmin" {
  source = "./modules/fortios/r/fortios_system_ssoadmin"

  # accprofile - (required) is a type of string
  accprofile = null
  # name - (optional) is a type of string
  name = null

  vdom = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accprofile" {
  description = "(required)"
  type        = string
}

variable "name" {
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
resource "fortios_system_ssoadmin" "this" {
  accprofile = var.accprofile
  name       = var.name

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
output "id" {
  description = "returns a string"
  value       = fortios_system_ssoadmin.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_ssoadmin.this.name
}

output "this" {
  value = fortios_system_ssoadmin.this
}
```

[top](#index)