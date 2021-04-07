# sdm_role

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
module "sdm_role" {
  source = "./modules/sdm/r/sdm_role"

  # composite - (optional) is a type of bool
  composite = null
  # name - (required) is a type of string
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
  description = "(required) - Unique human-readable name of the Role."
  type        = string
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

### Resource

```terraform
resource "sdm_role" "this" {
  # composite - (optional) is a type of bool
  composite = var.composite
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags

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
  value       = sdm_role.this.id
}

output "this" {
  value = sdm_role.this
}
```

[top](#index)