# exoscale_nlb

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_nlb" {
  source = "./modules/exoscale/r/exoscale_nlb"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # zone - (required) is a type of string
  zone = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
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
  description = "(required)"
  type        = string
}

variable "zone" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "exoscale_nlb" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # zone - (required) is a type of string
  zone = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = exoscale_nlb.this.created_at
}

output "id" {
  description = "returns a string"
  value       = exoscale_nlb.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = exoscale_nlb.this.ip_address
}

output "services" {
  description = "returns a set of string"
  value       = exoscale_nlb.this.services
}

output "state" {
  description = "returns a string"
  value       = exoscale_nlb.this.state
}

output "this" {
  value = exoscale_nlb.this
}
```

[top](#index)