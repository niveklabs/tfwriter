# exoscale_affinity

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
    exoscale = ">= 0.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_affinity" {
  source = "./modules/exoscale/r/exoscale_affinity"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null

  timeouts = [{
    create = null
    delete = null
    read   = null
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

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "exoscale_affinity" "this" {
  description = var.description
  name        = var.name
  type        = var.type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = exoscale_affinity.this.id
}

output "virtual_machine_ids" {
  description = "returns a set of string"
  value       = exoscale_affinity.this.virtual_machine_ids
}

output "this" {
  value = exoscale_affinity.this
}
```

[top](#index)