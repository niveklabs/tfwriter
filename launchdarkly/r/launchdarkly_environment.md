# launchdarkly_environment

[back](../launchdarkly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    launchdarkly = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "launchdarkly_environment" {
  source = "./modules/launchdarkly/r/launchdarkly_environment"

  # color - (required) is a type of string
  color = null
  # confirm_changes - (optional) is a type of bool
  confirm_changes = null
  # default_track_events - (optional) is a type of bool
  default_track_events = null
  # default_ttl - (optional) is a type of number
  default_ttl = null
  # key - (required) is a type of string
  key = null
  # name - (required) is a type of string
  name = null
  # project_key - (optional) is a type of string
  project_key = null
  # require_comments - (optional) is a type of bool
  require_comments = null
  # secure_mode - (optional) is a type of bool
  secure_mode = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "color" {
  description = "(required)"
  type        = string
}

variable "confirm_changes" {
  description = "(optional) - Whether or not to require confirmation for a flag and segment changes in this environment"
  type        = bool
  default     = null
}

variable "default_track_events" {
  description = "(optional) - Whether or not to send data export events for every flag created in the environment"
  type        = bool
  default     = null
}

variable "default_ttl" {
  description = "(optional) - The TTL for the environment. This must be between 0 and 60 minutes. The TTL setting only applies to environments using the PHP SDK."
  type        = number
  default     = null
}

variable "key" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "require_comments" {
  description = "(optional) - Whether or not to require comments for a flag and segment changes in this environment"
  type        = bool
  default     = null
}

variable "secure_mode" {
  description = "(optional) - Secure mode ensures a user of the client-side SDK cannot impersonate another user"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "launchdarkly_environment" "this" {
  color                = var.color
  confirm_changes      = var.confirm_changes
  default_track_events = var.default_track_events
  default_ttl          = var.default_ttl
  key                  = var.key
  name                 = var.name
  project_key          = var.project_key
  require_comments     = var.require_comments
  secure_mode          = var.secure_mode
  tags                 = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "api_key" {
  description = "returns a string"
  value       = launchdarkly_environment.this.api_key
  sensitive   = true
}

output "client_side_id" {
  description = "returns a string"
  value       = launchdarkly_environment.this.client_side_id
  sensitive   = true
}

output "confirm_changes" {
  description = "returns a bool"
  value       = launchdarkly_environment.this.confirm_changes
}

output "default_track_events" {
  description = "returns a bool"
  value       = launchdarkly_environment.this.default_track_events
}

output "default_ttl" {
  description = "returns a number"
  value       = launchdarkly_environment.this.default_ttl
}

output "id" {
  description = "returns a string"
  value       = launchdarkly_environment.this.id
}

output "mobile_key" {
  description = "returns a string"
  value       = launchdarkly_environment.this.mobile_key
  sensitive   = true
}

output "require_comments" {
  description = "returns a bool"
  value       = launchdarkly_environment.this.require_comments
}

output "secure_mode" {
  description = "returns a bool"
  value       = launchdarkly_environment.this.secure_mode
}

output "this" {
  value = launchdarkly_environment.this
}
```

[top](#index)