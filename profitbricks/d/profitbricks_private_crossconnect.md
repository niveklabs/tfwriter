# profitbricks_private_crossconnect

[back](../profitbricks.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/profitbricks/d/profitbricks_private_crossconnect"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
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

### Datasource

```terraform
data "profitbricks_private_crossconnect" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # default - (optional) is a type of string
      default = timeouts.value["default"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "connectable_datacenters" {
  description = "returns a list of object"
  value       = data.profitbricks_private_crossconnect.this.connectable_datacenters
}

output "id" {
  description = "returns a string"
  value       = data.profitbricks_private_crossconnect.this.id
}

output "peers" {
  description = "returns a list of object"
  value       = data.profitbricks_private_crossconnect.this.peers
}

output "this" {
  value = profitbricks_private_crossconnect.this
}
```

[top](#index)