# auth0_email_template

[back](../auth0.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    auth0 = ">= 0.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "auth0_email_template" {
  source = "./modules/auth0/r/auth0_email_template"

  # body - (required) is a type of string
  body = null
  # enabled - (required) is a type of bool
  enabled = null
  # from - (required) is a type of string
  from = null
  # result_url - (optional) is a type of string
  result_url = null
  # subject - (required) is a type of string
  subject = null
  # syntax - (required) is a type of string
  syntax = null
  # template - (required) is a type of string
  template = null
  # url_lifetime_in_seconds - (optional) is a type of number
  url_lifetime_in_seconds = null
}
```

[top](#index)

### Variables

```terraform
variable "body" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(required)"
  type        = bool
}

variable "from" {
  description = "(required)"
  type        = string
}

variable "result_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subject" {
  description = "(required)"
  type        = string
}

variable "syntax" {
  description = "(required)"
  type        = string
}

variable "template" {
  description = "(required)"
  type        = string
}

variable "url_lifetime_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "auth0_email_template" "this" {
  # body - (required) is a type of string
  body = var.body
  # enabled - (required) is a type of bool
  enabled = var.enabled
  # from - (required) is a type of string
  from = var.from
  # result_url - (optional) is a type of string
  result_url = var.result_url
  # subject - (required) is a type of string
  subject = var.subject
  # syntax - (required) is a type of string
  syntax = var.syntax
  # template - (required) is a type of string
  template = var.template
  # url_lifetime_in_seconds - (optional) is a type of number
  url_lifetime_in_seconds = var.url_lifetime_in_seconds
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = auth0_email_template.this.id
}

output "this" {
  value = auth0_email_template.this
}
```

[top](#index)