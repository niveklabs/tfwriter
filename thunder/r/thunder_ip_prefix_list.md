# thunder_ip_prefix_list

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_ip_prefix_list" {
  source = "./modules/thunder/r/thunder_ip_prefix_list"

  # name - (optional) is a type of string
  name = null
  # uuid - (optional) is a type of string
  uuid = null

  rules = [{
    action      = null
    any         = null
    description = null
    ge          = null
    ipaddr      = null
    le          = null
    seq         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action      = string
      any         = number
      description = string
      ge          = number
      ipaddr      = string
      le          = number
      seq         = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_ip_prefix_list" "this" {
  name = var.name
  uuid = var.uuid

  dynamic "rules" {
    for_each = var.rules
    content {
      action      = rules.value["action"]
      any         = rules.value["any"]
      description = rules.value["description"]
      ge          = rules.value["ge"]
      ipaddr      = rules.value["ipaddr"]
      le          = rules.value["le"]
      seq         = rules.value["seq"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_ip_prefix_list.this.id
}

output "this" {
  value = thunder_ip_prefix_list.this
}
```

[top](#index)