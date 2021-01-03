# panos_license_api_key

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
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_license_api_key" {
  source = "./modules/panos/r/panos_license_api_key"

  # key - (required) is a type of string
  key = null
  # retain_key - (optional) is a type of bool
  retain_key = null
}
```

[top](#index)

### Variables

```terraform
variable "key" {
  description = "(required)"
  type        = string
}

variable "retain_key" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_license_api_key" "this" {
  key        = var.key
  retain_key = var.retain_key
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_license_api_key.this.id
}

output "this" {
  value = panos_license_api_key.this
}
```

[top](#index)