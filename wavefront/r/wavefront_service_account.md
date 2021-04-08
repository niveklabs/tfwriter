# wavefront_service_account

[back](../wavefront.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    wavefront = ">= 2.8.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "wavefront_service_account" {
  source = "./modules/wavefront/r/wavefront_service_account"

  # active - (optional) is a type of bool
  active = null
  # description - (optional) is a type of string
  description = null
  # identifier - (required) is a type of string
  identifier = null
  # ingestion_policy - (optional) is a type of string
  ingestion_policy = null
  # permissions - (optional) is a type of set of string
  permissions = []
  # user_groups - (optional) is a type of set of string
  user_groups = []
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identifier" {
  description = "(required)"
  type        = string
}

variable "ingestion_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "permissions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "user_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "wavefront_service_account" "this" {
  # active - (optional) is a type of bool
  active = var.active
  # description - (optional) is a type of string
  description = var.description
  # identifier - (required) is a type of string
  identifier = var.identifier
  # ingestion_policy - (optional) is a type of string
  ingestion_policy = var.ingestion_policy
  # permissions - (optional) is a type of set of string
  permissions = var.permissions
  # user_groups - (optional) is a type of set of string
  user_groups = var.user_groups
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = wavefront_service_account.this.id
}

output "permissions" {
  description = "returns a set of string"
  value       = wavefront_service_account.this.permissions
}

output "user_groups" {
  description = "returns a set of string"
  value       = wavefront_service_account.this.user_groups
}

output "this" {
  value = wavefront_service_account.this
}
```

[top](#index)