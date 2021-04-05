# sdm_role

[back](../sdm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "sdm_role" {
  source = "./modules/sdm/d/sdm_role"

  # composite - (optional) is a type of bool
  composite = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "composite" {
  description = "(optional) - True if the Role is a composite role."
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - Unique human-readable name of the Role."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags is a map of key, value pairs."
  type        = map(string)
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

### Datasource

```terraform
data "sdm_role" "this" {
  composite = var.composite
  name      = var.name
  tags      = var.tags

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
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
  value       = data.sdm_role.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.sdm_role.this.ids
}

output "roles" {
  description = "returns a list of object"
  value       = data.sdm_role.this.roles
}

output "this" {
  value = sdm_role.this
}
```

[top](#index)