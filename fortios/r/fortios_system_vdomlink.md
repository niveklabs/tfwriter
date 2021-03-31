# fortios_system_vdomlink

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
module "fortios_system_vdomlink" {
  source = "./modules/fortios/r/fortios_system_vdomlink"

  # name - (optional) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null
  # vcluster - (optional) is a type of string
  vcluster = null
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

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcluster" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_vdomlink" "this" {
  name     = var.name
  type     = var.type
  vcluster = var.vcluster
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_vdomlink.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_vdomlink.this.name
}

output "type" {
  description = "returns a string"
  value       = fortios_system_vdomlink.this.type
}

output "vcluster" {
  description = "returns a string"
  value       = fortios_system_vdomlink.this.vcluster
}

output "this" {
  value = fortios_system_vdomlink.this
}
```

[top](#index)