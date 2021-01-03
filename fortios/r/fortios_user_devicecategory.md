# fortios_user_devicecategory

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
module "fortios_user_devicecategory" {
  source = "./modules/fortios/r/fortios_user_devicecategory"

  # comment - (optional) is a type of string
  comment = null
  # desc - (optional) is a type of string
  desc = null
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

variable "desc" {
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
resource "fortios_user_devicecategory" "this" {
  comment = var.comment
  desc    = var.desc
  name    = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_user_devicecategory.this.id
}

output "this" {
  value = fortios_user_devicecategory.this
}
```

[top](#index)