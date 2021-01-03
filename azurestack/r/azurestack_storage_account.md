# azurestack_storage_account

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurestack = ">= 0.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurestack_storage_account" {
  source = "./modules/azurestack/r/azurestack_storage_account"

  # account_encryption_source - (optional) is a type of string
  account_encryption_source = null
  # account_kind - (optional) is a type of string
  account_kind = null
  # account_replication_type - (required) is a type of string
  account_replication_type = null
  # account_tier - (required) is a type of string
  account_tier = null
  # account_type - (optional) is a type of string
  account_type = null
  # enable_blob_encryption - (optional) is a type of bool
  enable_blob_encryption = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  custom_domain = [{
    name          = null
    use_subdomain = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_encryption_source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "account_kind" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "account_replication_type" {
  description = "(required)"
  type        = string
}

variable "account_tier" {
  description = "(required)"
  type        = string
}

variable "account_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_blob_encryption" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "custom_domain" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name          = string
      use_subdomain = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_storage_account" "this" {
  account_encryption_source = var.account_encryption_source
  account_kind              = var.account_kind
  account_replication_type  = var.account_replication_type
  account_tier              = var.account_tier
  account_type              = var.account_type
  enable_blob_encryption    = var.enable_blob_encryption
  location                  = var.location
  name                      = var.name
  resource_group_name       = var.resource_group_name
  tags                      = var.tags

  dynamic "custom_domain" {
    for_each = var.custom_domain
    content {
      name          = custom_domain.value["name"]
      use_subdomain = custom_domain.value["use_subdomain"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_type" {
  description = "returns a string"
  value       = azurestack_storage_account.this.account_type
}

output "enable_blob_encryption" {
  description = "returns a bool"
  value       = azurestack_storage_account.this.enable_blob_encryption
}

output "id" {
  description = "returns a string"
  value       = azurestack_storage_account.this.id
}

output "primary_access_key" {
  description = "returns a string"
  value       = azurestack_storage_account.this.primary_access_key
}

output "primary_blob_connection_string" {
  description = "returns a string"
  value       = azurestack_storage_account.this.primary_blob_connection_string
}

output "primary_blob_endpoint" {
  description = "returns a string"
  value       = azurestack_storage_account.this.primary_blob_endpoint
}

output "primary_connection_string" {
  description = "returns a string"
  value       = azurestack_storage_account.this.primary_connection_string
}

output "primary_file_endpoint" {
  description = "returns a string"
  value       = azurestack_storage_account.this.primary_file_endpoint
}

output "primary_location" {
  description = "returns a string"
  value       = azurestack_storage_account.this.primary_location
}

output "primary_queue_endpoint" {
  description = "returns a string"
  value       = azurestack_storage_account.this.primary_queue_endpoint
}

output "primary_table_endpoint" {
  description = "returns a string"
  value       = azurestack_storage_account.this.primary_table_endpoint
}

output "secondary_access_key" {
  description = "returns a string"
  value       = azurestack_storage_account.this.secondary_access_key
}

output "secondary_blob_connection_string" {
  description = "returns a string"
  value       = azurestack_storage_account.this.secondary_blob_connection_string
}

output "secondary_blob_endpoint" {
  description = "returns a string"
  value       = azurestack_storage_account.this.secondary_blob_endpoint
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = azurestack_storage_account.this.secondary_connection_string
}

output "secondary_location" {
  description = "returns a string"
  value       = azurestack_storage_account.this.secondary_location
}

output "secondary_queue_endpoint" {
  description = "returns a string"
  value       = azurestack_storage_account.this.secondary_queue_endpoint
}

output "secondary_table_endpoint" {
  description = "returns a string"
  value       = azurestack_storage_account.this.secondary_table_endpoint
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_storage_account.this.tags
}

output "this" {
  value = azurestack_storage_account.this
}
```

[top](#index)