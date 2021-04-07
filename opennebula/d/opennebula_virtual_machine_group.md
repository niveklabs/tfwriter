# opennebula_virtual_machine_group

[back](../opennebula.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/opennebula/d/opennebula_virtual_machine_group"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the Virtual Machine Group"
  type        = string
}

variable "tags" {
  description = "(optional) - Add custom tags to the resource"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "opennebula_virtual_machine_group" "this" {
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.opennebula_virtual_machine_group.this.id
}

output "this" {
  value = opennebula_virtual_machine_group.this
}
```

[top](#index)