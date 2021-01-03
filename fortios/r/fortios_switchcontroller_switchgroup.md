# fortios_switchcontroller_switchgroup

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
module "fortios_switchcontroller_switchgroup" {
  source = "./modules/fortios/r/fortios_switchcontroller_switchgroup"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null

  members = [{
    name = null
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "members" {
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
resource "fortios_switchcontroller_switchgroup" "this" {
  description = var.description
  name        = var.name

  dynamic "members" {
    for_each = var.members
    content {
      name = members.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = fortios_switchcontroller_switchgroup.this.description
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_switchgroup.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_switchgroup.this.name
}

output "this" {
  value = fortios_switchcontroller_switchgroup.this
}
```

[top](#index)