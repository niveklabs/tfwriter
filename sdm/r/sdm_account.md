# sdm_account

[back](../sdm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/sdm/r/sdm_account"


  service = [{
    name      = null
    suspended = null
    tags      = {}
    token     = null
  }]

  timeouts = [{
    default = null
  }]

  user = [{
    email      = null
    first_name = null
    last_name  = null
    suspended  = null
    tags       = {}
  }]
}
```

[top](#index)

### Variables

```terraform
variable "service" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name      = string
      suspended = bool
      tags      = map(string)
      token     = string
    }
  ))
  default = []
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

variable "user" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      email      = string
      first_name = string
      last_name  = string
      suspended  = bool
      tags       = map(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "sdm_account" "this" {

  dynamic "service" {
    for_each = var.service
    content {
      # name - (required) is a type of string
      name = service.value["name"]
      # suspended - (optional) is a type of bool
      suspended = service.value["suspended"]
      # tags - (optional) is a type of map of string
      tags = service.value["tags"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

  dynamic "user" {
    for_each = var.user
    content {
      # email - (required) is a type of string
      email = user.value["email"]
      # first_name - (required) is a type of string
      first_name = user.value["first_name"]
      # last_name - (required) is a type of string
      last_name = user.value["last_name"]
      # suspended - (optional) is a type of bool
      suspended = user.value["suspended"]
      # tags - (optional) is a type of map of string
      tags = user.value["tags"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sdm_account.this.id
}

output "this" {
  value = sdm_account.this
}
```

[top](#index)