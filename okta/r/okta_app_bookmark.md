# okta_app_bookmark

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
module "okta_app_bookmark" {
  source = "./modules/okta/r/okta_app_bookmark"

  # auto_submit_toolbar - (optional) is a type of bool
  auto_submit_toolbar = null
  # groups - (optional) is a type of set of string
  groups = []
  # hide_ios - (optional) is a type of bool
  hide_ios = null
  # hide_web - (optional) is a type of bool
  hide_web = null
  # label - (required) is a type of string
  label = null
  # request_integration - (optional) is a type of bool
  request_integration = null
  # status - (optional) is a type of string
  status = null
  # url - (required) is a type of string
  url = null

  users = [{
    id       = null
    password = null
    scope    = null
    username = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_submit_toolbar" {
  description = "(optional) - Display auto submit toolbar"
  type        = bool
  default     = null
}

variable "groups" {
  description = "(optional) - Groups associated with the application"
  type        = set(string)
  default     = null
}

variable "hide_ios" {
  description = "(optional) - Do not display application icon on mobile app"
  type        = bool
  default     = null
}

variable "hide_web" {
  description = "(optional) - Do not display application icon to users"
  type        = bool
  default     = null
}

variable "label" {
  description = "(required) - Pretty name of app."
  type        = string
}

variable "request_integration" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "status" {
  description = "(optional) - Status of application."
  type        = string
  default     = null
}

variable "url" {
  description = "(required)"
  type        = string
}

variable "users" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id       = string
      password = string
      scope    = string
      username = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "okta_app_bookmark" "this" {
  # auto_submit_toolbar - (optional) is a type of bool
  auto_submit_toolbar = var.auto_submit_toolbar
  # groups - (optional) is a type of set of string
  groups = var.groups
  # hide_ios - (optional) is a type of bool
  hide_ios = var.hide_ios
  # hide_web - (optional) is a type of bool
  hide_web = var.hide_web
  # label - (required) is a type of string
  label = var.label
  # request_integration - (optional) is a type of bool
  request_integration = var.request_integration
  # status - (optional) is a type of string
  status = var.status
  # url - (required) is a type of string
  url = var.url

  dynamic "users" {
    for_each = var.users
    content {
      # id - (optional) is a type of string
      id = users.value["id"]
      # password - (optional) is a type of string
      password = users.value["password"]
      # username - (optional) is a type of string
      username = users.value["username"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_app_bookmark.this.id
}

output "name" {
  description = "returns a string"
  value       = okta_app_bookmark.this.name
}

output "sign_on_mode" {
  description = "returns a string"
  value       = okta_app_bookmark.this.sign_on_mode
}

output "this" {
  value = okta_app_bookmark.this
}
```

[top](#index)