# fortios_webfilter_ftgdlocalrating

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
module "fortios_webfilter_ftgdlocalrating" {
  source = "./modules/fortios/r/fortios_webfilter_ftgdlocalrating"

  # comment - (optional) is a type of string
  comment = null
  # rating - (required) is a type of string
  rating = null
  # status - (optional) is a type of string
  status = null
  # url - (optional) is a type of string
  url = null
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

variable "rating" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webfilter_ftgdlocalrating" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # rating - (required) is a type of string
  rating = var.rating
  # status - (optional) is a type of string
  status = var.status
  # url - (optional) is a type of string
  url = var.url
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_webfilter_ftgdlocalrating.this.id
}

output "status" {
  description = "returns a string"
  value       = fortios_webfilter_ftgdlocalrating.this.status
}

output "url" {
  description = "returns a string"
  value       = fortios_webfilter_ftgdlocalrating.this.url
}

output "this" {
  value = fortios_webfilter_ftgdlocalrating.this
}
```

[top](#index)