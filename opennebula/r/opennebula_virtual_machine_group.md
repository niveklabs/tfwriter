# opennebula_virtual_machine_group

[back](../opennebula.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opennebula = ">= 0.2.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opennebula_virtual_machine_group" {
  source = "./modules/opennebula/r/opennebula_virtual_machine_group"

  # group - (optional) is a type of string
  group = null
  # name - (required) is a type of string
  name = null
  # permissions - (optional) is a type of string
  permissions = null
  # tags - (optional) is a type of map of string
  tags = {}

  role = [{
    host_affined      = []
    host_anti_affined = []
    id                = null
    name              = null
    policy            = null
    vms               = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "group" {
  description = "(optional) - Name of the Group that onws the Template VM Group, If empty, it uses caller group"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the template"
  type        = string
}

variable "permissions" {
  description = "(optional) - Permissions for the template vm group (in Unix format, owner-group-other, use-manage-admin)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Add custom tags to the resource"
  type        = map(string)
  default     = null
}

variable "role" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      host_affined      = list(number)
      host_anti_affined = list(number)
      id                = number
      name              = string
      policy            = string
      vms               = list(number)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "opennebula_virtual_machine_group" "this" {
  # group - (optional) is a type of string
  group = var.group
  # name - (required) is a type of string
  name = var.name
  # permissions - (optional) is a type of string
  permissions = var.permissions
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "role" {
    for_each = var.role
    content {
      # host_affined - (optional) is a type of list of number
      host_affined = role.value["host_affined"]
      # host_anti_affined - (optional) is a type of list of number
      host_anti_affined = role.value["host_anti_affined"]
      # name - (required) is a type of string
      name = role.value["name"]
      # policy - (optional) is a type of string
      policy = role.value["policy"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "gid" {
  description = "returns a number"
  value       = opennebula_virtual_machine_group.this.gid
}

output "gname" {
  description = "returns a string"
  value       = opennebula_virtual_machine_group.this.gname
}

output "id" {
  description = "returns a string"
  value       = opennebula_virtual_machine_group.this.id
}

output "permissions" {
  description = "returns a string"
  value       = opennebula_virtual_machine_group.this.permissions
}

output "uid" {
  description = "returns a number"
  value       = opennebula_virtual_machine_group.this.uid
}

output "uname" {
  description = "returns a string"
  value       = opennebula_virtual_machine_group.this.uname
}

output "this" {
  value = opennebula_virtual_machine_group.this
}
```

[top](#index)