# fortios_webfilter_ftgdlocalcat

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
module "fortios_webfilter_ftgdlocalcat" {
  source = "./modules/fortios/r/fortios_webfilter_ftgdlocalcat"

  # desc - (optional) is a type of string
  desc = null
  # fosid - (optional) is a type of number
  fosid = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "desc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webfilter_ftgdlocalcat" "this" {
  # desc - (optional) is a type of string
  desc = var.desc
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "desc" {
  description = "returns a string"
  value       = fortios_webfilter_ftgdlocalcat.this.desc
}

output "fosid" {
  description = "returns a number"
  value       = fortios_webfilter_ftgdlocalcat.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_webfilter_ftgdlocalcat.this.id
}

output "status" {
  description = "returns a string"
  value       = fortios_webfilter_ftgdlocalcat.this.status
}

output "this" {
  value = fortios_webfilter_ftgdlocalcat.this
}
```

[top](#index)