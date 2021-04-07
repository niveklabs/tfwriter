# rancher2_bootstrap

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_bootstrap" {
  source = "./modules/rancher2/r/rancher2_bootstrap"

  # current_password - (optional) is a type of string
  current_password = null
  # password - (optional) is a type of string
  password = null
  # telemetry - (optional) is a type of bool
  telemetry = null
  # token_ttl - (optional) is a type of number
  token_ttl = null
  # token_update - (optional) is a type of bool
  token_update = null
  # ui_default_landing - (optional) is a type of string
  ui_default_landing = null
}
```

[top](#index)

### Variables

```terraform
variable "current_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "telemetry" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "token_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "token_update" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ui_default_landing" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_bootstrap" "this" {
  # current_password - (optional) is a type of string
  current_password = var.current_password
  # password - (optional) is a type of string
  password = var.password
  # telemetry - (optional) is a type of bool
  telemetry = var.telemetry
  # token_ttl - (optional) is a type of number
  token_ttl = var.token_ttl
  # token_update - (optional) is a type of bool
  token_update = var.token_update
  # ui_default_landing - (optional) is a type of string
  ui_default_landing = var.ui_default_landing
}
```

[top](#index)

### Outputs

```terraform
output "current_password" {
  description = "returns a string"
  value       = rancher2_bootstrap.this.current_password
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = rancher2_bootstrap.this.id
}

output "password" {
  description = "returns a string"
  value       = rancher2_bootstrap.this.password
  sensitive   = true
}

output "temp_token" {
  description = "returns a string"
  value       = rancher2_bootstrap.this.temp_token
  sensitive   = true
}

output "temp_token_id" {
  description = "returns a string"
  value       = rancher2_bootstrap.this.temp_token_id
}

output "token" {
  description = "returns a string"
  value       = rancher2_bootstrap.this.token
  sensitive   = true
}

output "token_id" {
  description = "returns a string"
  value       = rancher2_bootstrap.this.token_id
}

output "url" {
  description = "returns a string"
  value       = rancher2_bootstrap.this.url
}

output "user" {
  description = "returns a string"
  value       = rancher2_bootstrap.this.user
}

output "this" {
  value = rancher2_bootstrap.this
}
```

[top](#index)