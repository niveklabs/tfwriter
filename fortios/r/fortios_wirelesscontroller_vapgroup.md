# fortios_wirelesscontroller_vapgroup

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
module "fortios_wirelesscontroller_vapgroup" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_vapgroup"

  # comment - (optional) is a type of string
  comment = null
  # name - (required) is a type of string
  name = null

  vaps = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "vaps" {
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
resource "fortios_wirelesscontroller_vapgroup" "this" {
  comment = var.comment
  name    = var.name

  dynamic "vaps" {
    for_each = var.vaps
    content {
      name = vaps.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_vapgroup.this.id
}

output "this" {
  value = fortios_wirelesscontroller_vapgroup.this
}
```

[top](#index)