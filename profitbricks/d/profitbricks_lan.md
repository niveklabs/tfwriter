# profitbricks_lan

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
module "profitbricks_lan" {
  source = "./modules/profitbricks/d/profitbricks_lan"

  # datacenter_id - (required) is a type of string
  datacenter_id = null
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
variable "datacenter_id" {
  description = "(required)"
  type        = string
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
data "profitbricks_lan" "this" {
  # datacenter_id - (required) is a type of string
  datacenter_id = var.datacenter_id
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
output "id" {
  description = "returns a string"
  value       = data.profitbricks_lan.this.id
}

output "ip_failover" {
  description = "returns a list of object"
  value       = data.profitbricks_lan.this.ip_failover
}

output "pcc" {
  description = "returns a string"
  value       = data.profitbricks_lan.this.pcc
}

output "public" {
  description = "returns a bool"
  value       = data.profitbricks_lan.this.public
}

output "this" {
  value = profitbricks_lan.this
}
```

[top](#index)