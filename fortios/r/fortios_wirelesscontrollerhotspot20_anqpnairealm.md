# fortios_wirelesscontrollerhotspot20_anqpnairealm

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
module "fortios_wirelesscontrollerhotspot20_anqpnairealm" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_anqpnairealm"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null

  nai_list = [{
    eap_method = [{
      auth_param = [{
        id    = null
        index = null
        val   = null
      }]
      index  = null
      method = null
    }]
    encoding  = null
    nai_realm = null
    name      = null
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nai_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      eap_method = list(object(
        {
          auth_param = list(object(
            {
              id    = string
              index = number
              val   = string
            }
          ))
          index  = number
          method = string
        }
      ))
      encoding  = string
      nai_realm = string
      name      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontrollerhotspot20_anqpnairealm" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  name                  = var.name

  dynamic "nai_list" {
    for_each = var.nai_list
    content {
      encoding  = nai_list.value["encoding"]
      nai_realm = nai_list.value["nai_realm"]
      name      = nai_list.value["name"]

      dynamic "eap_method" {
        for_each = nai_list.value.eap_method
        content {
          index  = eap_method.value["index"]
          method = eap_method.value["method"]

          dynamic "auth_param" {
            for_each = eap_method.value.auth_param
            content {
              id    = auth_param.value["id"]
              index = auth_param.value["index"]
              val   = auth_param.value["val"]
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
  value       = fortios_wirelesscontrollerhotspot20_anqpnairealm.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_anqpnairealm.this.name
}

output "this" {
  value = fortios_wirelesscontrollerhotspot20_anqpnairealm.this
}
```

[top](#index)