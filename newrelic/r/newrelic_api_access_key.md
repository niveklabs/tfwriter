# newrelic_api_access_key

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_api_access_key" {
  source = "./modules/newrelic/r/newrelic_api_access_key"

  # account_id - (required) is a type of number
  account_id = null
  # ingest_type - (optional) is a type of string
  ingest_type = null
  # key_type - (required) is a type of string
  key_type = null
  # name - (optional) is a type of string
  name = null
  # notes - (optional) is a type of string
  notes = null
  # user_id - (optional) is a type of number
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required)"
  type        = number
}

variable "ingest_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_type" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_id" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_api_access_key" "this" {
  # account_id - (required) is a type of number
  account_id = var.account_id
  # ingest_type - (optional) is a type of string
  ingest_type = var.ingest_type
  # key_type - (required) is a type of string
  key_type = var.key_type
  # name - (optional) is a type of string
  name = var.name
  # notes - (optional) is a type of string
  notes = var.notes
  # user_id - (optional) is a type of number
  user_id = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = newrelic_api_access_key.this.id
}

output "ingest_type" {
  description = "returns a string"
  value       = newrelic_api_access_key.this.ingest_type
}

output "key" {
  description = "returns a string"
  value       = newrelic_api_access_key.this.key
  sensitive   = true
}

output "name" {
  description = "returns a string"
  value       = newrelic_api_access_key.this.name
}

output "notes" {
  description = "returns a string"
  value       = newrelic_api_access_key.this.notes
}

output "user_id" {
  description = "returns a number"
  value       = newrelic_api_access_key.this.user_id
}

output "this" {
  value = newrelic_api_access_key.this
}
```

[top](#index)