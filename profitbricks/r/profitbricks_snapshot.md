# profitbricks_snapshot

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
module "profitbricks_snapshot" {
  source = "./modules/profitbricks/r/profitbricks_snapshot"

  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # name - (required) is a type of string
  name = null
  # volume_id - (required) is a type of string
  volume_id = null

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
variable "datacenter_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "volume_id" {
  description = "(required)"
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
resource "profitbricks_snapshot" "this" {
  datacenter_id = var.datacenter_id
  name          = var.name
  volume_id     = var.volume_id

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
  value       = profitbricks_snapshot.this.id
}

output "this" {
  value = profitbricks_snapshot.this
}
```

[top](#index)