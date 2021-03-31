# fortios_switchcontroller_switchinterfacetag

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
module "fortios_switchcontroller_switchinterfacetag" {
  source = "./modules/fortios/r/fortios_switchcontroller_switchinterfacetag"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_switchinterfacetag" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_switchinterfacetag.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_switchinterfacetag.this.name
}

output "this" {
  value = fortios_switchcontroller_switchinterfacetag.this
}
```

[top](#index)