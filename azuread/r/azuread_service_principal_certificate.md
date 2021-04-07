# azuread_service_principal_certificate

[back](../azuread.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuread = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuread_service_principal_certificate" {
  source = "./modules/azuread/r/azuread_service_principal_certificate"

  # encoding - (optional) is a type of string
  encoding = null
  # end_date - (optional) is a type of string
  end_date = null
  # end_date_relative - (optional) is a type of string
  end_date_relative = null
  # key_id - (optional) is a type of string
  key_id = null
  # service_principal_id - (required) is a type of string
  service_principal_id = null
  # start_date - (optional) is a type of string
  start_date = null
  # type - (optional) is a type of string
  type = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "encoding" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_date_relative" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_principal_id" {
  description = "(required)"
  type        = string
}

variable "start_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "azuread_service_principal_certificate" "this" {
  # encoding - (optional) is a type of string
  encoding = var.encoding
  # end_date - (optional) is a type of string
  end_date = var.end_date
  # end_date_relative - (optional) is a type of string
  end_date_relative = var.end_date_relative
  # key_id - (optional) is a type of string
  key_id = var.key_id
  # service_principal_id - (required) is a type of string
  service_principal_id = var.service_principal_id
  # start_date - (optional) is a type of string
  start_date = var.start_date
  # type - (optional) is a type of string
  type = var.type
  # value - (required) is a type of string
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "end_date" {
  description = "returns a string"
  value       = azuread_service_principal_certificate.this.end_date
}

output "id" {
  description = "returns a string"
  value       = azuread_service_principal_certificate.this.id
}

output "key_id" {
  description = "returns a string"
  value       = azuread_service_principal_certificate.this.key_id
}

output "start_date" {
  description = "returns a string"
  value       = azuread_service_principal_certificate.this.start_date
}

output "this" {
  value = azuread_service_principal_certificate.this
}
```

[top](#index)