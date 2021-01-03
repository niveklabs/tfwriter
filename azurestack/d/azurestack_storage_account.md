# azurestack_storage_account

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/azurestack/d/azurestack_storage_account"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "azurestack_storage_account" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
}
```

[top](#index)

### Outputs

```terraform
output "account_encryption_source" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.account_encryption_source
}

output "account_kind" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.account_kind
}

output "account_replication_type" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.account_replication_type
}

output "account_tier" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.account_tier
}

output "custom_domain" {
  description = "returns a list of object"
  value       = data.azurestack_storage_account.this.custom_domain
}

output "enable_blob_encryption" {
  description = "returns a bool"
  value       = data.azurestack_storage_account.this.enable_blob_encryption
}

output "id" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.location
}

output "primary_access_key" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.primary_access_key
}

output "primary_blob_connection_string" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.primary_blob_connection_string
}

output "primary_blob_endpoint" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.primary_blob_endpoint
}

output "primary_connection_string" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.primary_connection_string
}

output "primary_file_endpoint" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.primary_file_endpoint
}

output "primary_location" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.primary_location
}

output "primary_queue_endpoint" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.primary_queue_endpoint
}

output "primary_table_endpoint" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.primary_table_endpoint
}

output "secondary_access_key" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.secondary_access_key
}

output "secondary_blob_connection_string" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.secondary_blob_connection_string
}

output "secondary_blob_endpoint" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.secondary_blob_endpoint
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.secondary_connection_string
}

output "secondary_location" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.secondary_location
}

output "secondary_queue_endpoint" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.secondary_queue_endpoint
}

output "secondary_table_endpoint" {
  description = "returns a string"
  value       = data.azurestack_storage_account.this.secondary_table_endpoint
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurestack_storage_account.this.tags
}

output "this" {
  value = azurestack_storage_account.this
}
```

[top](#index)