# dome9_cloudaccount_azure

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.21.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_cloudaccount_azure" {
  source = "./modules/dome9/r/dome9_cloudaccount_azure"

  # client_id - (required) is a type of string
  client_id = null
  # client_password - (required) is a type of string
  client_password = null
  # name - (required) is a type of string
  name = null
  # operation_mode - (required) is a type of string
  operation_mode = null
  # organizational_unit_id - (optional) is a type of string
  organizational_unit_id = null
  # subscription_id - (required) is a type of string
  subscription_id = null
  # tenant_id - (required) is a type of string
  tenant_id = null
}
```

[top](#index)

### Variables

```terraform
variable "client_id" {
  description = "(required)"
  type        = string
}

variable "client_password" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "operation_mode" {
  description = "(required)"
  type        = string
}

variable "organizational_unit_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subscription_id" {
  description = "(required)"
  type        = string
}

variable "tenant_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "dome9_cloudaccount_azure" "this" {
  client_id              = var.client_id
  client_password        = var.client_password
  name                   = var.name
  operation_mode         = var.operation_mode
  organizational_unit_id = var.organizational_unit_id
  subscription_id        = var.subscription_id
  tenant_id              = var.tenant_id
}
```

[top](#index)

### Outputs

```terraform
output "creation_date" {
  description = "returns a string"
  value       = dome9_cloudaccount_azure.this.creation_date
}

output "id" {
  description = "returns a string"
  value       = dome9_cloudaccount_azure.this.id
}

output "organizational_unit_name" {
  description = "returns a string"
  value       = dome9_cloudaccount_azure.this.organizational_unit_name
}

output "organizational_unit_path" {
  description = "returns a string"
  value       = dome9_cloudaccount_azure.this.organizational_unit_path
}

output "vendor" {
  description = "returns a string"
  value       = dome9_cloudaccount_azure.this.vendor
}

output "this" {
  value = dome9_cloudaccount_azure.this
}
```

[top](#index)