# onelogin_auth_servers

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
module "onelogin_auth_servers" {
  source = "./modules/onelogin/r/onelogin_auth_servers"

  # description - (required) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  configuration = [{
    access_token_expiration_minutes  = null
    audiences                        = []
    refresh_token_expiration_minutes = null
    resource_identifier              = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "configuration" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      access_token_expiration_minutes  = number
      audiences                        = list(string)
      refresh_token_expiration_minutes = number
      resource_identifier              = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "onelogin_auth_servers" "this" {
  # description - (required) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name

  dynamic "configuration" {
    for_each = var.configuration
    content {
      # access_token_expiration_minutes - (optional) is a type of number
      access_token_expiration_minutes = configuration.value["access_token_expiration_minutes"]
      # audiences - (required) is a type of list of string
      audiences = configuration.value["audiences"]
      # refresh_token_expiration_minutes - (optional) is a type of number
      refresh_token_expiration_minutes = configuration.value["refresh_token_expiration_minutes"]
      # resource_identifier - (required) is a type of string
      resource_identifier = configuration.value["resource_identifier"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = onelogin_auth_servers.this.id
}

output "this" {
  value = onelogin_auth_servers.this
}
```

[top](#index)