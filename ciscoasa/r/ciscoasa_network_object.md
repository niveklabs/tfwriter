# ciscoasa_network_object

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
module "ciscoasa_network_object" {
  source = "./modules/ciscoasa/r/ciscoasa_network_object"

  # name - (required) is a type of string
  name = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ciscoasa_network_object" "this" {
  # name - (required) is a type of string
  name = var.name
  # value - (required) is a type of string
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ciscoasa_network_object.this.id
}

output "this" {
  value = ciscoasa_network_object.this
}
```

[top](#index)