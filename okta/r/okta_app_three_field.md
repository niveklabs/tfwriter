# okta_app_three_field

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
    okta = ">= 3.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_app_three_field" {
  source = "./modules/okta/r/okta_app_three_field"

  # accessibility_error_redirect_url - (optional) is a type of string
  accessibility_error_redirect_url = null
  # accessibility_self_service - (optional) is a type of bool
  accessibility_self_service = null
  # auto_submit_toolbar - (optional) is a type of bool
  auto_submit_toolbar = null
  # button_selector - (required) is a type of string
  button_selector = null
  # extra_field_selector - (required) is a type of string
  extra_field_selector = null
  # extra_field_value - (required) is a type of string
  extra_field_value = null
  # groups - (optional) is a type of set of string
  groups = []
  # hide_ios - (optional) is a type of bool
  hide_ios = null
  # hide_web - (optional) is a type of bool
  hide_web = null
  # label - (required) is a type of string
  label = null
  # password_selector - (required) is a type of string
  password_selector = null
  # status - (optional) is a type of string
  status = null
  # url - (required) is a type of string
  url = null
  # url_regex - (optional) is a type of string
  url_regex = null
  # user_name_template - (optional) is a type of string
  user_name_template = null
  # user_name_template_suffix - (optional) is a type of string
  user_name_template_suffix = null
  # user_name_template_type - (optional) is a type of string
  user_name_template_type = null
  # username_selector - (required) is a type of string
  username_selector = null

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
variable "accessibility_error_redirect_url" {
  description = "(optional) - Custom error page URL"
  type        = string
  default     = null
}

variable "accessibility_self_service" {
  description = "(optional) - Enable self service"
  type        = bool
  default     = null
}

variable "auto_submit_toolbar" {
  description = "(optional) - Display auto submit toolbar"
  type        = bool
  default     = null
}

variable "button_selector" {
  description = "(required) - Login button field CSS selector"
  type        = string
}

variable "extra_field_selector" {
  description = "(required) - Extra field CSS selector"
  type        = string
}

variable "extra_field_value" {
  description = "(required) - Value for extra form field"
  type        = string
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

variable "password_selector" {
  description = "(required) - Login password field CSS selector"
  type        = string
}

variable "status" {
  description = "(optional) - Status of application."
  type        = string
  default     = null
}

variable "url" {
  description = "(required) - Login URL"
  type        = string
}

variable "url_regex" {
  description = "(optional) - A regex that further restricts URL to the specified regex"
  type        = string
  default     = null
}

variable "user_name_template" {
  description = "(optional) - Username template"
  type        = string
  default     = null
}

variable "user_name_template_suffix" {
  description = "(optional) - Username template suffix"
  type        = string
  default     = null
}

variable "user_name_template_type" {
  description = "(optional) - Username template type"
  type        = string
  default     = null
}

variable "username_selector" {
  description = "(required) - Login username field CSS selector"
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
resource "okta_app_three_field" "this" {
  accessibility_error_redirect_url = var.accessibility_error_redirect_url
  accessibility_self_service       = var.accessibility_self_service
  auto_submit_toolbar              = var.auto_submit_toolbar
  button_selector                  = var.button_selector
  extra_field_selector             = var.extra_field_selector
  extra_field_value                = var.extra_field_value
  groups                           = var.groups
  hide_ios                         = var.hide_ios
  hide_web                         = var.hide_web
  label                            = var.label
  password_selector                = var.password_selector
  status                           = var.status
  url                              = var.url
  url_regex                        = var.url_regex
  user_name_template               = var.user_name_template
  user_name_template_suffix        = var.user_name_template_suffix
  user_name_template_type          = var.user_name_template_type
  username_selector                = var.username_selector

  dynamic "users" {
    for_each = var.users
    content {
      id       = users.value["id"]
      password = users.value["password"]
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
  value       = okta_app_three_field.this.id
}

output "name" {
  description = "returns a string"
  value       = okta_app_three_field.this.name
}

output "sign_on_mode" {
  description = "returns a string"
  value       = okta_app_three_field.this.sign_on_mode
}

output "this" {
  value = okta_app_three_field.this
}
```

[top](#index)