# sdm_account

[back](../sdm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sdm = ">= 1.0.19"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sdm_account" {
  source = "./modules/sdm/d/sdm_account"

  # email - (optional) is a type of string
  email = null
  # first_name - (optional) is a type of string
  first_name = null
  # last_name - (optional) is a type of string
  last_name = null
  # name - (optional) is a type of string
  name = null
  # suspended - (optional) is a type of bool
  suspended = null
  # type - (optional) is a type of string
  type = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "first_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "last_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "suspended" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "sdm_account" "this" {
  # email - (optional) is a type of string
  email = var.email
  # first_name - (optional) is a type of string
  first_name = var.first_name
  # last_name - (optional) is a type of string
  last_name = var.last_name
  # name - (optional) is a type of string
  name = var.name
  # suspended - (optional) is a type of bool
  suspended = var.suspended
  # type - (optional) is a type of string
  type = var.type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "accounts" {
  description = "returns a list of object"
  value       = data.sdm_account.this.accounts
}

output "id" {
  description = "returns a string"
  value       = data.sdm_account.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.sdm_account.this.ids
}

output "this" {
  value = sdm_account.this
}
```

[top](#index)