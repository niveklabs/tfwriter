# fortios_user_securityexemptlist

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_user_securityexemptlist" {
  source = "./modules/fortios/r/fortios_user_securityexemptlist"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null

  rule = [{
    devices = [{
      name = null
    }]
    dstaddr = [{
      name = null
    }]
    id = null
    service = [{
      name = null
    }]
    srcaddr = [{
      name = null
    }]
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

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      devices = list(object(
        {
          name = string
        }
      ))
      dstaddr = list(object(
        {
          name = string
        }
      ))
      id = number
      service = list(object(
        {
          name = string
        }
      ))
      srcaddr = list(object(
        {
          name = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_securityexemptlist" "this" {
  description = var.description
  name        = var.name

  dynamic "rule" {
    for_each = var.rule
    content {
      id = rule.value["id"]

      dynamic "devices" {
        for_each = rule.value.devices
        content {
          name = devices.value["name"]
        }
      }

      dynamic "dstaddr" {
        for_each = rule.value.dstaddr
        content {
          name = dstaddr.value["name"]
        }
      }

      dynamic "service" {
        for_each = rule.value.service
        content {
          name = service.value["name"]
        }
      }

      dynamic "srcaddr" {
        for_each = rule.value.srcaddr
        content {
          name = srcaddr.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = fortios_user_securityexemptlist.this.description
}

output "id" {
  description = "returns a string"
  value       = fortios_user_securityexemptlist.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_user_securityexemptlist.this.name
}

output "this" {
  value = fortios_user_securityexemptlist.this
}
```

[top](#index)