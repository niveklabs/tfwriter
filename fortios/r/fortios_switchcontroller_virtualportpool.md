# fortios_switchcontroller_virtualportpool

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
module "fortios_switchcontroller_virtualportpool" {
  source = "./modules/fortios/r/fortios_switchcontroller_virtualportpool"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
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
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_virtualportpool" "this" {
  description = var.description
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = fortios_switchcontroller_virtualportpool.this.description
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_virtualportpool.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_virtualportpool.this.name
}

output "this" {
  value = fortios_switchcontroller_virtualportpool.this
}
```

[top](#index)