# scaleway_rdb_user

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_rdb_user" {
  source = "./modules/scaleway/r/scaleway_rdb_user"

  # instance_id - (required) is a type of string
  instance_id = null
  # is_admin - (optional) is a type of bool
  is_admin = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
  # region - (optional) is a type of string
  region = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required) - Instance on which the user is created"
  type        = string
}

variable "is_admin" {
  description = "(optional) - Grant admin permissions to database user"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Database user name"
  type        = string
}

variable "password" {
  description = "(required) - Database user password"
  type        = string
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
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

### Resource

```terraform
resource "scaleway_rdb_user" "this" {
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # is_admin - (optional) is a type of bool
  is_admin = var.is_admin
  # name - (required) is a type of string
  name = var.name
  # password - (required) is a type of string
  password = var.password
  # region - (optional) is a type of string
  region = var.region

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
output "id" {
  description = "returns a string"
  value       = scaleway_rdb_user.this.id
}

output "region" {
  description = "returns a string"
  value       = scaleway_rdb_user.this.region
}

output "this" {
  value = scaleway_rdb_user.this
}
```

[top](#index)