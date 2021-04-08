# auth0_role

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
module "auth0_role" {
  source = "./modules/auth0/r/auth0_role"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # user_ids - (optional) is a type of list of string
  user_ids = []

  permissions = [{
    name                       = null
    resource_server_identifier = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "user_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "permissions" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name                       = string
      resource_server_identifier = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "auth0_role" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # user_ids - (optional) is a type of list of string
  user_ids = var.user_ids

  dynamic "permissions" {
    for_each = var.permissions
    content {
      # name - (required) is a type of string
      name = permissions.value["name"]
      # resource_server_identifier - (required) is a type of string
      resource_server_identifier = permissions.value["resource_server_identifier"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = auth0_role.this.id
}

output "this" {
  value = auth0_role.this
}
```

[top](#index)