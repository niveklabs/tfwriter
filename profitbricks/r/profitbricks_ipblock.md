# profitbricks_ipblock

[back](../profitbricks.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    profitbricks = ">= 1.6.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "profitbricks_ipblock" {
  source = "./modules/profitbricks/r/profitbricks_ipblock"

  # location - (required) is a type of string
  location = null
  # name - (optional) is a type of string
  name = null
  # size - (required) is a type of number
  size = null

  timeouts = [{
    create  = null
    default = null
    delete  = null
    update  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size" {
  description = "(required)"
  type        = number
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
      update  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "profitbricks_ipblock" "this" {
  location = var.location
  name     = var.name
  size     = var.size

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create  = timeouts.value["create"]
      default = timeouts.value["default"]
      delete  = timeouts.value["delete"]
      update  = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = profitbricks_ipblock.this.id
}

output "ips" {
  description = "returns a list of string"
  value       = profitbricks_ipblock.this.ips
}

output "this" {
  value = profitbricks_ipblock.this
}
```

[top](#index)