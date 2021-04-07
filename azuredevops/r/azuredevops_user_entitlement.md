# azuredevops_user_entitlement

[back](../azuredevops.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuredevops = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_user_entitlement" {
  source = "./modules/azuredevops/r/azuredevops_user_entitlement"

  # account_license_type - (optional) is a type of string
  account_license_type = null
  # licensing_source - (optional) is a type of string
  licensing_source = null
  # origin - (optional) is a type of string
  origin = null
  # origin_id - (optional) is a type of string
  origin_id = null
  # principal_name - (optional) is a type of string
  principal_name = null
}
```

[top](#index)

### Variables

```terraform
variable "account_license_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "licensing_source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "origin" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "origin_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "principal_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_user_entitlement" "this" {
  # account_license_type - (optional) is a type of string
  account_license_type = var.account_license_type
  # licensing_source - (optional) is a type of string
  licensing_source = var.licensing_source
  # origin - (optional) is a type of string
  origin = var.origin
  # origin_id - (optional) is a type of string
  origin_id = var.origin_id
  # principal_name - (optional) is a type of string
  principal_name = var.principal_name
}
```

[top](#index)

### Outputs

```terraform
output "descriptor" {
  description = "returns a string"
  value       = azuredevops_user_entitlement.this.descriptor
}

output "id" {
  description = "returns a string"
  value       = azuredevops_user_entitlement.this.id
}

output "origin" {
  description = "returns a string"
  value       = azuredevops_user_entitlement.this.origin
}

output "origin_id" {
  description = "returns a string"
  value       = azuredevops_user_entitlement.this.origin_id
}

output "principal_name" {
  description = "returns a string"
  value       = azuredevops_user_entitlement.this.principal_name
}

output "this" {
  value = azuredevops_user_entitlement.this
}
```

[top](#index)