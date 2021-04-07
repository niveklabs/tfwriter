# checkpoint_management_login

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_login" {
  source = "./modules/checkpoint/r/checkpoint_management_login"

  # continue_last_session - (optional) is a type of bool
  continue_last_session = null
  # domain - (optional) is a type of string
  domain = null
  # enter_last_published_session - (optional) is a type of bool
  enter_last_published_session = null
  # password - (required) is a type of string
  password = null
  # read_only - (optional) is a type of bool
  read_only = null
  # session_comments - (optional) is a type of string
  session_comments = null
  # session_description - (optional) is a type of string
  session_description = null
  # session_name - (optional) is a type of string
  session_name = null
  # session_timeout - (optional) is a type of number
  session_timeout = null
  # user - (required) is a type of string
  user = null
}
```

[top](#index)

### Variables

```terraform
variable "continue_last_session" {
  description = "(optional) - When 'continue-last-session' is set to 'True', the new session would continue where the last session was stopped. This option is available when the administrator has only one session that can be continued. If there is more than one session, see 'switch-session' API."
  type        = bool
  default     = null
}

variable "domain" {
  description = "(optional) - Use domain to login to specific domain. Domain can be identified by name or UID."
  type        = string
  default     = null
}

variable "enter_last_published_session" {
  description = "(optional) - Login to the last published session. Such login is done with the Read Only permissions."
  type        = bool
  default     = null
}

variable "password" {
  description = "(required) - Administrator password."
  type        = string
}

variable "read_only" {
  description = "(optional) - Login with Read Only permissions. This parameter is not considered in case continue-last-session is true."
  type        = bool
  default     = null
}

variable "session_comments" {
  description = "(optional) - Session comments."
  type        = string
  default     = null
}

variable "session_description" {
  description = "(optional) - Session description."
  type        = string
  default     = null
}

variable "session_name" {
  description = "(optional) - Session unique name."
  type        = string
  default     = null
}

variable "session_timeout" {
  description = "(optional) - Session expiration timeout in seconds. Default 600 seconds."
  type        = number
  default     = null
}

variable "user" {
  description = "(required) - Administrator user name."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_login" "this" {
  # continue_last_session - (optional) is a type of bool
  continue_last_session = var.continue_last_session
  # domain - (optional) is a type of string
  domain = var.domain
  # enter_last_published_session - (optional) is a type of bool
  enter_last_published_session = var.enter_last_published_session
  # password - (required) is a type of string
  password = var.password
  # read_only - (optional) is a type of bool
  read_only = var.read_only
  # session_comments - (optional) is a type of string
  session_comments = var.session_comments
  # session_description - (optional) is a type of string
  session_description = var.session_description
  # session_name - (optional) is a type of string
  session_name = var.session_name
  # session_timeout - (optional) is a type of number
  session_timeout = var.session_timeout
  # user - (required) is a type of string
  user = var.user
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_login.this.id
}

output "this" {
  value = checkpoint_management_login.this
}
```

[top](#index)