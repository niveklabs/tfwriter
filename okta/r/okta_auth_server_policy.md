# okta_auth_server_policy

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
module "okta_auth_server_policy" {
  source = "./modules/okta/r/okta_auth_server_policy"

  # auth_server_id - (required) is a type of string
  auth_server_id = null
  # client_whitelist - (required) is a type of set of string
  client_whitelist = []
  # description - (required) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # priority - (required) is a type of number
  priority = null
  # status - (optional) is a type of string
  status = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_server_id" {
  description = "(required)"
  type        = string
}

variable "client_whitelist" {
  description = "(required) - Use [\"ALL_CLIENTS\"] when unsure."
  type        = set(string)
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(required) - Priority of the auth server policy"
  type        = number
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Auth server policy type, unlikely this will be anything other then the default"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_auth_server_policy" "this" {
  # auth_server_id - (required) is a type of string
  auth_server_id = var.auth_server_id
  # client_whitelist - (required) is a type of set of string
  client_whitelist = var.client_whitelist
  # description - (required) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # priority - (required) is a type of number
  priority = var.priority
  # status - (optional) is a type of string
  status = var.status
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_auth_server_policy.this.id
}

output "this" {
  value = okta_auth_server_policy.this
}
```

[top](#index)