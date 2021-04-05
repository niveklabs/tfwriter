# panos_licensing

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_licensing" {
  source = "./modules/panos/r/panos_licensing"

  # auth_codes - (required) is a type of list of string
  auth_codes = []
  # delicense - (optional) is a type of bool
  delicense = null
  # mode - (optional) is a type of string
  mode = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_codes" {
  description = "(required)"
  type        = list(string)
}

variable "delicense" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_licensing" "this" {
  auth_codes = var.auth_codes
  delicense  = var.delicense
  mode       = var.mode
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_licensing.this.id
}

output "licenses" {
  description = "returns a list of object"
  value       = panos_licensing.this.licenses
}

output "this" {
  value = panos_licensing.this
}
```

[top](#index)