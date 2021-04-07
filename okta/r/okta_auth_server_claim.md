# okta_auth_server_claim

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_auth_server_claim" {
  source = "./modules/okta/r/okta_auth_server_claim"

  # always_include_in_token - (optional) is a type of bool
  always_include_in_token = null
  # auth_server_id - (required) is a type of string
  auth_server_id = null
  # claim_type - (required) is a type of string
  claim_type = null
  # group_filter_type - (optional) is a type of string
  group_filter_type = null
  # name - (required) is a type of string
  name = null
  # scopes - (optional) is a type of set of string
  scopes = []
  # status - (optional) is a type of string
  status = null
  # value - (required) is a type of string
  value = null
  # value_type - (optional) is a type of string
  value_type = null
}
```

[top](#index)

### Variables

```terraform
variable "always_include_in_token" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auth_server_id" {
  description = "(required) - Auth server ID"
  type        = string
}

variable "claim_type" {
  description = "(required)"
  type        = string
}

variable "group_filter_type" {
  description = "(optional) - Required when value_type is GROUPS"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Auth server claim name"
  type        = string
}

variable "scopes" {
  description = "(optional) - Auth server claim list of scopes"
  type        = set(string)
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "value" {
  description = "(required)"
  type        = string
}

variable "value_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_auth_server_claim" "this" {
  # always_include_in_token - (optional) is a type of bool
  always_include_in_token = var.always_include_in_token
  # auth_server_id - (required) is a type of string
  auth_server_id = var.auth_server_id
  # claim_type - (required) is a type of string
  claim_type = var.claim_type
  # group_filter_type - (optional) is a type of string
  group_filter_type = var.group_filter_type
  # name - (required) is a type of string
  name = var.name
  # scopes - (optional) is a type of set of string
  scopes = var.scopes
  # status - (optional) is a type of string
  status = var.status
  # value - (required) is a type of string
  value = var.value
  # value_type - (optional) is a type of string
  value_type = var.value_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_auth_server_claim.this.id
}

output "this" {
  value = okta_auth_server_claim.this
}
```

[top](#index)