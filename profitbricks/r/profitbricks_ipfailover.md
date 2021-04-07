# profitbricks_ipfailover

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
module "profitbricks_ipfailover" {
  source = "./modules/profitbricks/r/profitbricks_ipfailover"

  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # ip - (required) is a type of string
  ip = null
  # lan_id - (required) is a type of string
  lan_id = null
  # nicuuid - (required) is a type of string
  nicuuid = null

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

variable "ip" {
  description = "(required)"
  type        = string
}

variable "lan_id" {
  description = "(required)"
  type        = string
}

variable "nicuuid" {
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
resource "profitbricks_ipfailover" "this" {
  # datacenter_id - (required) is a type of string
  datacenter_id = var.datacenter_id
  # ip - (required) is a type of string
  ip = var.ip
  # lan_id - (required) is a type of string
  lan_id = var.lan_id
  # nicuuid - (required) is a type of string
  nicuuid = var.nicuuid

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
  value       = profitbricks_ipfailover.this.id
}

output "this" {
  value = profitbricks_ipfailover.this
}
```

[top](#index)