# profitbricks_private_crossconnect

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
module "profitbricks_private_crossconnect" {
  source = "./modules/profitbricks/r/profitbricks_private_crossconnect"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

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
variable "description" {
  description = "(optional) - The desired description for the private cross-connect"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The desired name for the private cross-connect"
  type        = string
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
resource "profitbricks_private_crossconnect" "this" {
  description = var.description
  name        = var.name

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
output "connectable_datacenters" {
  description = "returns a list of object"
  value       = profitbricks_private_crossconnect.this.connectable_datacenters
}

output "id" {
  description = "returns a string"
  value       = profitbricks_private_crossconnect.this.id
}

output "peers" {
  description = "returns a list of object"
  value       = profitbricks_private_crossconnect.this.peers
}

output "this" {
  value = profitbricks_private_crossconnect.this
}
```

[top](#index)