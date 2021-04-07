# checkpoint_management_access_role

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
module "checkpoint_management_access_role" {
  source = "./modules/checkpoint/r/checkpoint_management_access_role"

  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # name - (required) is a type of string
  name = null
  # networks - (optional) is a type of set of string
  networks = []
  # remote_access_clients - (optional) is a type of string
  remote_access_clients = null
  # tags - (optional) is a type of set of string
  tags = []

  machines = [{
    base_dn   = null
    selection = []
    source    = null
  }]

  users = [{
    base_dn   = null
    selection = []
    source    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "color" {
  description = "(optional) - Color of the object. Should be one of existing colors."
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "ignore_errors" {
  description = "(optional) - Apply changes ignoring errors. You won't be able to publish such a changes. If ignore-warnings flag was omitted - warnings will also be ignored."
  type        = bool
  default     = null
}

variable "ignore_warnings" {
  description = "(optional) - Apply changes ignoring warnings."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Object name."
  type        = string
}

variable "networks" {
  description = "(optional) - Collection of Network objects identified by the name or UID that can access the system."
  type        = set(string)
  default     = null
}

variable "remote_access_clients" {
  description = "(optional) - Remote access clients identified by name or UID."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "machines" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      base_dn   = string
      selection = set(string)
      source    = string
    }
  ))
  default = []
}

variable "users" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      base_dn   = string
      selection = set(string)
      source    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_access_role" "this" {
  # color - (optional) is a type of string
  color = var.color
  # comments - (optional) is a type of string
  comments = var.comments
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # name - (required) is a type of string
  name = var.name
  # networks - (optional) is a type of set of string
  networks = var.networks
  # remote_access_clients - (optional) is a type of string
  remote_access_clients = var.remote_access_clients
  # tags - (optional) is a type of set of string
  tags = var.tags

  dynamic "machines" {
    for_each = var.machines
    content {
      # base_dn - (optional) is a type of string
      base_dn = machines.value["base_dn"]
      # selection - (optional) is a type of set of string
      selection = machines.value["selection"]
      # source - (optional) is a type of string
      source = machines.value["source"]
    }
  }

  dynamic "users" {
    for_each = var.users
    content {
      # base_dn - (optional) is a type of string
      base_dn = users.value["base_dn"]
      # selection - (optional) is a type of set of string
      selection = users.value["selection"]
      # source - (optional) is a type of string
      source = users.value["source"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_access_role.this.id
}

output "this" {
  value = checkpoint_management_access_role.this
}
```

[top](#index)