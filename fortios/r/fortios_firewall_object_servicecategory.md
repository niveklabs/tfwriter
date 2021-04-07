# fortios_firewall_object_servicecategory

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
module "fortios_firewall_object_servicecategory" {
  source = "./modules/fortios/r/fortios_firewall_object_servicecategory"

  # comment - (optional) is a type of string
  comment = null
  # name - (required) is a type of string
  name = null
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
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_object_servicecategory" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewall_object_servicecategory.this.id
}

output "this" {
  value = fortios_firewall_object_servicecategory.this
}
```

[top](#index)