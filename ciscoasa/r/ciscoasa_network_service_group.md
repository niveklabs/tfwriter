# ciscoasa_network_service_group

[back](../ciscoasa.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ciscoasa = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ciscoasa_network_service_group" {
  source = "./modules/ciscoasa/r/ciscoasa_network_service_group"

  # members - (required) is a type of set of string
  members = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "members" {
  description = "(required)"
  type        = set(string)
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ciscoasa_network_service_group" "this" {
  # members - (required) is a type of set of string
  members = var.members
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ciscoasa_network_service_group.this.id
}

output "this" {
  value = ciscoasa_network_service_group.this
}
```

[top](#index)