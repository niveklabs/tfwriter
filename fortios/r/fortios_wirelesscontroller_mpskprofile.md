# fortios_wirelesscontroller_mpskprofile

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_wirelesscontroller_mpskprofile" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_mpskprofile"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # mpsk_concurrent_clients - (optional) is a type of number
  mpsk_concurrent_clients = null
  # name - (optional) is a type of string
  name = null

  mpsk_group = [{
    mpsk_key = [{
      comment                      = null
      concurrent_client_limit_type = null
      concurrent_clients           = null
      mac                          = null
      mpsk_schedules = [{
        name = null
      }]
      name       = null
      passphrase = null
    }]
    name      = null
    vlan_id   = null
    vlan_type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mpsk_concurrent_clients" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mpsk_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      mpsk_key = list(object(
        {
          comment                      = string
          concurrent_client_limit_type = string
          concurrent_clients           = number
          mac                          = string
          mpsk_schedules = list(object(
            {
              name = string
            }
          ))
          name       = string
          passphrase = string
        }
      ))
      name      = string
      vlan_id   = number
      vlan_type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_mpskprofile" "this" {
  dynamic_sort_subtable   = var.dynamic_sort_subtable
  mpsk_concurrent_clients = var.mpsk_concurrent_clients
  name                    = var.name

  dynamic "mpsk_group" {
    for_each = var.mpsk_group
    content {
      name      = mpsk_group.value["name"]
      vlan_id   = mpsk_group.value["vlan_id"]
      vlan_type = mpsk_group.value["vlan_type"]

      dynamic "mpsk_key" {
        for_each = mpsk_group.value.mpsk_key
        content {
          comment                      = mpsk_key.value["comment"]
          concurrent_client_limit_type = mpsk_key.value["concurrent_client_limit_type"]
          concurrent_clients           = mpsk_key.value["concurrent_clients"]
          mac                          = mpsk_key.value["mac"]
          name                         = mpsk_key.value["name"]
          passphrase                   = mpsk_key.value["passphrase"]

          dynamic "mpsk_schedules" {
            for_each = mpsk_key.value.mpsk_schedules
            content {
              name = mpsk_schedules.value["name"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_mpskprofile.this.id
}

output "mpsk_concurrent_clients" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_mpskprofile.this.mpsk_concurrent_clients
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_mpskprofile.this.name
}

output "this" {
  value = fortios_wirelesscontroller_mpskprofile.this
}
```

[top](#index)