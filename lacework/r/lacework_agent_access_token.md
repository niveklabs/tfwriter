# lacework_agent_access_token

[back](../lacework.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    lacework = ">= 0.3.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "lacework_agent_access_token" {
  source = "./modules/lacework/r/lacework_agent_access_token"

  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "lacework_agent_access_token" "this" {
  description = var.description
  enabled     = var.enabled
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "account" {
  description = "returns a string"
  value       = lacework_agent_access_token.this.account
}

output "created_time" {
  description = "returns a string"
  value       = lacework_agent_access_token.this.created_time
}

output "id" {
  description = "returns a string"
  value       = lacework_agent_access_token.this.id
}

output "last_updated_time" {
  description = "returns a string"
  value       = lacework_agent_access_token.this.last_updated_time
}

output "token" {
  description = "returns a string"
  value       = lacework_agent_access_token.this.token
  sensitive   = true
}

output "version" {
  description = "returns a string"
  value       = lacework_agent_access_token.this.version
}

output "this" {
  value = lacework_agent_access_token.this
}
```

[top](#index)