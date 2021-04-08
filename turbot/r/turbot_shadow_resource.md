# turbot_shadow_resource

[back](../turbot.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    turbot = ">= 1.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "turbot_shadow_resource" {
  source = "./modules/turbot/r/turbot_shadow_resource"

  # filter - (optional) is a type of string
  filter = null
  # resource - (optional) is a type of string
  resource = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "turbot_shadow_resource" "this" {
  # filter - (optional) is a type of string
  filter = var.filter
  # resource - (optional) is a type of string
  resource = var.resource

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = turbot_shadow_resource.this.id
}

output "this" {
  value = turbot_shadow_resource.this
}
```

[top](#index)