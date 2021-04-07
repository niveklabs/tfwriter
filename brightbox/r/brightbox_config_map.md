# brightbox_config_map

[back](../brightbox.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    brightbox = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "brightbox_config_map" {
  source = "./modules/brightbox/r/brightbox_config_map"

  # data - (required) is a type of map of string
  data = {}
  # name - (optional) is a type of string
  name = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "data" {
  description = "(required) - keys/values making up the ConfigMap"
  type        = map(string)
}

variable "name" {
  description = "(optional) - User editable label"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "brightbox_config_map" "this" {
  # data - (required) is a type of map of string
  data = var.data
  # name - (optional) is a type of string
  name = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = brightbox_config_map.this.id
}

output "this" {
  value = brightbox_config_map.this
}
```

[top](#index)