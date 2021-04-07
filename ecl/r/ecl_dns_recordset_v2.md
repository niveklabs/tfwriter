# ecl_dns_recordset_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_dns_recordset_v2" {
  source = "./modules/ecl/r/ecl_dns_recordset_v2"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # record - (required) is a type of string
  record = null
  # ttl - (required) is a type of number
  ttl = null
  # type - (required) is a type of string
  type = null
  # zone_id - (required) is a type of string
  zone_id = null

  timeouts = [{
    create = null
    delete = null
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

variable "record" {
  description = "(required)"
  type        = string
}

variable "ttl" {
  description = "(required)"
  type        = number
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ecl_dns_recordset_v2" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # record - (required) is a type of string
  record = var.record
  # ttl - (required) is a type of number
  ttl = var.ttl
  # type - (required) is a type of string
  type = var.type
  # zone_id - (required) is a type of string
  zone_id = var.zone_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
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
  value       = ecl_dns_recordset_v2.this.id
}

output "this" {
  value = ecl_dns_recordset_v2.this
}
```

[top](#index)