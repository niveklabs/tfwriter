# gitlab_deploy_token

[back](../gitlab.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gitlab = ">= 3.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_deploy_token" {
  source = "./modules/gitlab/r/gitlab_deploy_token"

  # expires_at - (optional) is a type of string
  expires_at = null
  # group - (optional) is a type of string
  group = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # scopes - (required) is a type of set of string
  scopes = []
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "expires_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scopes" {
  description = "(required)"
  type        = set(string)
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_deploy_token" "this" {
  expires_at = var.expires_at
  group      = var.group
  name       = var.name
  project    = var.project
  scopes     = var.scopes
  username   = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_deploy_token.this.id
}

output "token" {
  description = "returns a string"
  value       = gitlab_deploy_token.this.token
  sensitive   = true
}

output "username" {
  description = "returns a string"
  value       = gitlab_deploy_token.this.username
}

output "this" {
  value = gitlab_deploy_token.this
}
```

[top](#index)