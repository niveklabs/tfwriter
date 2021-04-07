# profitbricks_lan

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
module "profitbricks_lan" {
  source = "./modules/profitbricks/r/profitbricks_lan"

  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # name - (optional) is a type of string
  name = null
  # pcc - (optional) is a type of string
  pcc = null
  # public - (required) is a type of bool
  public = null

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

variable "pcc" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public" {
  description = "(required)"
  type        = bool
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
resource "profitbricks_lan" "this" {
  # datacenter_id - (required) is a type of string
  datacenter_id = var.datacenter_id
  # name - (optional) is a type of string
  name = var.name
  # pcc - (optional) is a type of string
  pcc = var.pcc
  # public - (required) is a type of bool
  public = var.public

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
  value       = profitbricks_lan.this.id
}

output "this" {
  value = profitbricks_lan.this
}
```

[top](#index)