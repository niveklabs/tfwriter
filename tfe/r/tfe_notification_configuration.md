# tfe_notification_configuration

[back](../tfe.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tfe = ">= 0.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tfe_notification_configuration" {
  source = "./modules/tfe/r/tfe_notification_configuration"

  # destination_type - (required) is a type of string
  destination_type = null
  # email_addresses - (optional) is a type of set of string
  email_addresses = []
  # email_user_ids - (optional) is a type of set of string
  email_user_ids = []
  # enabled - (optional) is a type of bool
  enabled = null
  # name - (required) is a type of string
  name = null
  # token - (optional) is a type of string
  token = null
  # triggers - (optional) is a type of set of string
  triggers = []
  # url - (optional) is a type of string
  url = null
  # workspace_id - (required) is a type of string
  workspace_id = null
}
```

[top](#index)

### Variables

```terraform
variable "destination_type" {
  description = "(required)"
  type        = string
}

variable "email_addresses" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "email_user_ids" {
  description = "(optional)"
  type        = set(string)
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

variable "token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "triggers" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "workspace_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tfe_notification_configuration" "this" {
  # destination_type - (required) is a type of string
  destination_type = var.destination_type
  # email_addresses - (optional) is a type of set of string
  email_addresses = var.email_addresses
  # email_user_ids - (optional) is a type of set of string
  email_user_ids = var.email_user_ids
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # name - (required) is a type of string
  name = var.name
  # token - (optional) is a type of string
  token = var.token
  # triggers - (optional) is a type of set of string
  triggers = var.triggers
  # url - (optional) is a type of string
  url = var.url
  # workspace_id - (required) is a type of string
  workspace_id = var.workspace_id
}
```

[top](#index)

### Outputs

```terraform
output "email_addresses" {
  description = "returns a set of string"
  value       = tfe_notification_configuration.this.email_addresses
}

output "email_user_ids" {
  description = "returns a set of string"
  value       = tfe_notification_configuration.this.email_user_ids
}

output "id" {
  description = "returns a string"
  value       = tfe_notification_configuration.this.id
}

output "this" {
  value = tfe_notification_configuration.this
}
```

[top](#index)