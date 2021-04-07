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
    fortios = ">= 1.11.0"
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
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fortilink - (optional) is a type of string
  fortilink = null
  # name - (optional) is a type of string
  name = null

  members = [{
    name      = null
    switch_id = null
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

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortilink" {
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
      name      = string
      switch_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_switchgroup" "this" {
  # description - (optional) is a type of string
  description = var.description
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # fortilink - (optional) is a type of string
  fortilink = var.fortilink
  # name - (optional) is a type of string
  name = var.name

  dynamic "members" {
    for_each = var.members
    content {
      # name - (optional) is a type of string
      name = members.value["name"]
      # switch_id - (optional) is a type of string
      switch_id = members.value["switch_id"]
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

output "fortilink" {
  description = "returns a string"
  value       = fortios_switchcontroller_switchgroup.this.fortilink
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