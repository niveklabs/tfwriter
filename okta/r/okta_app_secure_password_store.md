# okta_app_secure_password_store

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
module "okta_app_secure_password_store" {
  source = "./modules/okta/r/okta_app_secure_password_store"

  # accessibility_error_redirect_url - (optional) is a type of string
  accessibility_error_redirect_url = null
  # accessibility_self_service - (optional) is a type of bool
  accessibility_self_service = null
  # auto_submit_toolbar - (optional) is a type of bool
  auto_submit_toolbar = null
  # credentials_scheme - (optional) is a type of string
  credentials_scheme = null
  # groups - (optional) is a type of set of string
  groups = []
  # hide_ios - (optional) is a type of bool
  hide_ios = null
  # hide_web - (optional) is a type of bool
  hide_web = null
  # label - (required) is a type of string
  label = null
  # optional_field1 - (optional) is a type of string
  optional_field1 = null
  # optional_field1_value - (optional) is a type of string
  optional_field1_value = null
  # optional_field2 - (optional) is a type of string
  optional_field2 = null
  # optional_field2_value - (optional) is a type of string
  optional_field2_value = null
  # optional_field3 - (optional) is a type of string
  optional_field3 = null
  # optional_field3_value - (optional) is a type of string
  optional_field3_value = null
  # password_field - (required) is a type of string
  password_field = null
  # reveal_password - (optional) is a type of bool
  reveal_password = null
  # shared_password - (optional) is a type of string
  shared_password = null
  # shared_username - (optional) is a type of string
  shared_username = null
  # status - (optional) is a type of string
  status = null
  # url - (required) is a type of string
  url = null
  # user_name_template - (optional) is a type of string
  user_name_template = null
  # user_name_template_suffix - (optional) is a type of string
  user_name_template_suffix = null
  # user_name_template_type - (optional) is a type of string
  user_name_template_type = null
  # username_field - (required) is a type of string
  username_field = null

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

variable "credentials_scheme" {
  description = "(optional) - Application credentials scheme"
  type        = string
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

variable "optional_field1" {
  description = "(optional) - Name of optional param in the login form"
  type        = string
  default     = null
}

variable "optional_field1_value" {
  description = "(optional) - Name of optional value in login form"
  type        = string
  default     = null
}

variable "optional_field2" {
  description = "(optional) - Name of optional param in the login form"
  type        = string
  default     = null
}

variable "optional_field2_value" {
  description = "(optional) - Name of optional value in login form"
  type        = string
  default     = null
}

variable "optional_field3" {
  description = "(optional) - Name of optional param in the login form"
  type        = string
  default     = null
}

variable "optional_field3_value" {
  description = "(optional) - Name of optional value in login form"
  type        = string
  default     = null
}

variable "password_field" {
  description = "(required) - Login password field"
  type        = string
}

variable "reveal_password" {
  description = "(optional) - Allow user to reveal password"
  type        = bool
  default     = null
}

variable "shared_password" {
  description = "(optional) - Shared password, required for certain schemes."
  type        = string
  default     = null
}

variable "shared_username" {
  description = "(optional) - Shared username, required for certain schemes."
  type        = string
  default     = null
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

variable "username_field" {
  description = "(required) - Login username field"
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
resource "okta_app_secure_password_store" "this" {
  # accessibility_error_redirect_url - (optional) is a type of string
  accessibility_error_redirect_url = var.accessibility_error_redirect_url
  # accessibility_self_service - (optional) is a type of bool
  accessibility_self_service = var.accessibility_self_service
  # auto_submit_toolbar - (optional) is a type of bool
  auto_submit_toolbar = var.auto_submit_toolbar
  # credentials_scheme - (optional) is a type of string
  credentials_scheme = var.credentials_scheme
  # groups - (optional) is a type of set of string
  groups = var.groups
  # hide_ios - (optional) is a type of bool
  hide_ios = var.hide_ios
  # hide_web - (optional) is a type of bool
  hide_web = var.hide_web
  # label - (required) is a type of string
  label = var.label
  # optional_field1 - (optional) is a type of string
  optional_field1 = var.optional_field1
  # optional_field1_value - (optional) is a type of string
  optional_field1_value = var.optional_field1_value
  # optional_field2 - (optional) is a type of string
  optional_field2 = var.optional_field2
  # optional_field2_value - (optional) is a type of string
  optional_field2_value = var.optional_field2_value
  # optional_field3 - (optional) is a type of string
  optional_field3 = var.optional_field3
  # optional_field3_value - (optional) is a type of string
  optional_field3_value = var.optional_field3_value
  # password_field - (required) is a type of string
  password_field = var.password_field
  # reveal_password - (optional) is a type of bool
  reveal_password = var.reveal_password
  # shared_password - (optional) is a type of string
  shared_password = var.shared_password
  # shared_username - (optional) is a type of string
  shared_username = var.shared_username
  # status - (optional) is a type of string
  status = var.status
  # url - (required) is a type of string
  url = var.url
  # user_name_template - (optional) is a type of string
  user_name_template = var.user_name_template
  # user_name_template_suffix - (optional) is a type of string
  user_name_template_suffix = var.user_name_template_suffix
  # user_name_template_type - (optional) is a type of string
  user_name_template_type = var.user_name_template_type
  # username_field - (required) is a type of string
  username_field = var.username_field

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
  value       = okta_app_secure_password_store.this.id
}

output "name" {
  description = "returns a string"
  value       = okta_app_secure_password_store.this.name
}

output "sign_on_mode" {
  description = "returns a string"
  value       = okta_app_secure_password_store.this.sign_on_mode
}

output "this" {
  value = okta_app_secure_password_store.this
}
```

[top](#index)