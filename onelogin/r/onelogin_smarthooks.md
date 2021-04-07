# onelogin_smarthooks

[back](../onelogin.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    onelogin = ">= 0.1.12"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "onelogin_smarthooks" {
  source = "./modules/onelogin/r/onelogin_smarthooks"

  # context_version - (optional) is a type of string
  context_version = null
  # disabled - (required) is a type of bool
  disabled = null
  # env_vars - (required) is a type of list of string
  env_vars = []
  # function - (required) is a type of string
  function = null
  # options - (optional) is a type of map of string
  options = {}
  # packages - (required) is a type of map of string
  packages = {}
  # retries - (required) is a type of number
  retries = null
  # runtime - (required) is a type of string
  runtime = null
  # timeout - (required) is a type of number
  timeout = null
  # type - (required) is a type of string
  type = null

  conditions = [{
    operator = null
    source   = null
    value    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "context_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disabled" {
  description = "(required)"
  type        = bool
}

variable "env_vars" {
  description = "(required)"
  type        = list(string)
}

variable "function" {
  description = "(required)"
  type        = string
}

variable "options" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "packages" {
  description = "(required)"
  type        = map(string)
}

variable "retries" {
  description = "(required)"
  type        = number
}

variable "runtime" {
  description = "(required)"
  type        = string
}

variable "timeout" {
  description = "(required)"
  type        = number
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "conditions" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      operator = string
      source   = string
      value    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "onelogin_smarthooks" "this" {
  # context_version - (optional) is a type of string
  context_version = var.context_version
  # disabled - (required) is a type of bool
  disabled = var.disabled
  # env_vars - (required) is a type of list of string
  env_vars = var.env_vars
  # function - (required) is a type of string
  function = var.function
  # options - (optional) is a type of map of string
  options = var.options
  # packages - (required) is a type of map of string
  packages = var.packages
  # retries - (required) is a type of number
  retries = var.retries
  # runtime - (required) is a type of string
  runtime = var.runtime
  # timeout - (required) is a type of number
  timeout = var.timeout
  # type - (required) is a type of string
  type = var.type

  dynamic "conditions" {
    for_each = var.conditions
    content {
      # operator - (required) is a type of string
      operator = conditions.value["operator"]
      # source - (required) is a type of string
      source = conditions.value["source"]
      # value - (required) is a type of string
      value = conditions.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "context_version" {
  description = "returns a string"
  value       = onelogin_smarthooks.this.context_version
}

output "created_at" {
  description = "returns a string"
  value       = onelogin_smarthooks.this.created_at
}

output "id" {
  description = "returns a string"
  value       = onelogin_smarthooks.this.id
}

output "status" {
  description = "returns a string"
  value       = onelogin_smarthooks.this.status
}

output "updated_at" {
  description = "returns a string"
  value       = onelogin_smarthooks.this.updated_at
}

output "this" {
  value = onelogin_smarthooks.this
}
```

[top](#index)