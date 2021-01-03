# opsgenie_user

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opsgenie = ">= 0.5.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_user" {
  source = "./modules/opsgenie/r/opsgenie_user"

  # full_name - (required) is a type of string
  full_name = null
  # locale - (optional) is a type of string
  locale = null
  # role - (required) is a type of string
  role = null
  # skype_username - (optional) is a type of string
  skype_username = null
  # tags - (optional) is a type of set of string
  tags = []
  # timezone - (optional) is a type of string
  timezone = null
  # user_details - (optional) is a type of map of string
  user_details = {}
  # username - (required) is a type of string
  username = null

  user_address = [{
    city    = null
    country = null
    line    = null
    state   = null
    zipcode = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "full_name" {
  description = "(required)"
  type        = string
}

variable "locale" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "skype_username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_details" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}

variable "user_address" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      city    = string
      country = string
      line    = string
      state   = string
      zipcode = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "opsgenie_user" "this" {
  full_name      = var.full_name
  locale         = var.locale
  role           = var.role
  skype_username = var.skype_username
  tags           = var.tags
  timezone       = var.timezone
  user_details   = var.user_details
  username       = var.username

  dynamic "user_address" {
    for_each = var.user_address
    content {
      city    = user_address.value["city"]
      country = user_address.value["country"]
      line    = user_address.value["line"]
      state   = user_address.value["state"]
      zipcode = user_address.value["zipcode"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opsgenie_user.this.id
}

output "this" {
  value = opsgenie_user.this
}
```

[top](#index)