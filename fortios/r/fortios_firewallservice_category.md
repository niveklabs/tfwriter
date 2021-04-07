# fortios_firewallservice_category

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
module "fortios_firewallservice_category" {
  source = "./modules/fortios/r/fortios_firewallservice_category"

  # comment - (optional) is a type of string
  comment = null
  # name - (optional) is a type of string
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
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewallservice_category" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewallservice_category.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewallservice_category.this.name
}

output "this" {
  value = fortios_firewallservice_category.this
}
```

[top](#index)