# brightbox_server_group

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
module "brightbox_server_group" {
  source = "./modules/brightbox/r/brightbox_server_group"

  # description - (optional) is a type of string
  description = null
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
variable "description" {
  description = "(optional) - User editable label"
  type        = string
  default     = null
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
resource "brightbox_server_group" "this" {
  description = var.description
  name        = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default" {
  description = "returns a bool"
  value       = brightbox_server_group.this.default
}

output "fqdn" {
  description = "returns a string"
  value       = brightbox_server_group.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = brightbox_server_group.this.id
}

output "this" {
  value = brightbox_server_group.this
}
```

[top](#index)