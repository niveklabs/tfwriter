# pagerduty_user

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    pagerduty = ">= 1.9.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_user" {
  source = "./modules/pagerduty/r/pagerduty_user"

  # color - (optional) is a type of string
  color = null
  # description - (optional) is a type of string
  description = null
  # email - (required) is a type of string
  email = null
  # job_title - (optional) is a type of string
  job_title = null
  # name - (required) is a type of string
  name = null
  # role - (optional) is a type of string
  role = null
  # teams - (optional) is a type of set of string
  teams = []
  # time_zone - (optional) is a type of string
  time_zone = null
}
```

[top](#index)

### Variables

```terraform
variable "color" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "job_title" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "teams" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "time_zone" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_user" "this" {
  # color - (optional) is a type of string
  color = var.color
  # description - (optional) is a type of string
  description = var.description
  # email - (required) is a type of string
  email = var.email
  # job_title - (optional) is a type of string
  job_title = var.job_title
  # name - (required) is a type of string
  name = var.name
  # role - (optional) is a type of string
  role = var.role
  # teams - (optional) is a type of set of string
  teams = var.teams
  # time_zone - (optional) is a type of string
  time_zone = var.time_zone
}
```

[top](#index)

### Outputs

```terraform
output "avatar_url" {
  description = "returns a string"
  value       = pagerduty_user.this.avatar_url
}

output "color" {
  description = "returns a string"
  value       = pagerduty_user.this.color
}

output "html_url" {
  description = "returns a string"
  value       = pagerduty_user.this.html_url
}

output "id" {
  description = "returns a string"
  value       = pagerduty_user.this.id
}

output "invitation_sent" {
  description = "returns a bool"
  value       = pagerduty_user.this.invitation_sent
}

output "teams" {
  description = "returns a set of string"
  value       = pagerduty_user.this.teams
}

output "time_zone" {
  description = "returns a string"
  value       = pagerduty_user.this.time_zone
}

output "this" {
  value = pagerduty_user.this
}
```

[top](#index)