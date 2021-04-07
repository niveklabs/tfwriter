# heroku_app

[back](../heroku.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    heroku = ">= 4.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_app" {
  source = "./modules/heroku/r/heroku_app"

  # acm - (optional) is a type of bool
  acm = null
  # buildpacks - (optional) is a type of list of string
  buildpacks = []
  # config_vars - (optional) is a type of map of string
  config_vars = {}
  # internal_routing - (optional) is a type of bool
  internal_routing = null
  # name - (required) is a type of string
  name = null
  # region - (required) is a type of string
  region = null
  # sensitive_config_vars - (optional) is a type of map of string
  sensitive_config_vars = {}
  # space - (optional) is a type of string
  space = null
  # stack - (optional) is a type of string
  stack = null

  organization = [{
    locked   = null
    name     = null
    personal = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acm" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "buildpacks" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "config_vars" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "internal_routing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "sensitive_config_vars" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "space" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "organization" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      locked   = bool
      name     = string
      personal = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "heroku_app" "this" {
  # acm - (optional) is a type of bool
  acm = var.acm
  # buildpacks - (optional) is a type of list of string
  buildpacks = var.buildpacks
  # config_vars - (optional) is a type of map of string
  config_vars = var.config_vars
  # internal_routing - (optional) is a type of bool
  internal_routing = var.internal_routing
  # name - (required) is a type of string
  name = var.name
  # region - (required) is a type of string
  region = var.region
  # sensitive_config_vars - (optional) is a type of map of string
  sensitive_config_vars = var.sensitive_config_vars
  # space - (optional) is a type of string
  space = var.space
  # stack - (optional) is a type of string
  stack = var.stack

  dynamic "organization" {
    for_each = var.organization
    content {
      # locked - (optional) is a type of bool
      locked = organization.value["locked"]
      # name - (required) is a type of string
      name = organization.value["name"]
      # personal - (optional) is a type of bool
      personal = organization.value["personal"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "acm" {
  description = "returns a bool"
  value       = heroku_app.this.acm
}

output "all_config_vars" {
  description = "returns a map of string"
  value       = heroku_app.this.all_config_vars
  sensitive   = true
}

output "buildpacks" {
  description = "returns a list of string"
  value       = heroku_app.this.buildpacks
}

output "config_vars" {
  description = "returns a map of string"
  value       = heroku_app.this.config_vars
}

output "git_url" {
  description = "returns a string"
  value       = heroku_app.this.git_url
}

output "heroku_hostname" {
  description = "returns a string"
  value       = heroku_app.this.heroku_hostname
}

output "id" {
  description = "returns a string"
  value       = heroku_app.this.id
}

output "internal_routing" {
  description = "returns a bool"
  value       = heroku_app.this.internal_routing
}

output "sensitive_config_vars" {
  description = "returns a map of string"
  value       = heroku_app.this.sensitive_config_vars
  sensitive   = true
}

output "stack" {
  description = "returns a string"
  value       = heroku_app.this.stack
}

output "uuid" {
  description = "returns a string"
  value       = heroku_app.this.uuid
}

output "web_url" {
  description = "returns a string"
  value       = heroku_app.this.web_url
}

output "this" {
  value = heroku_app.this
}
```

[top](#index)