# thunder_fw_radius_server

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_fw_radius_server" {
  source = "./modules/thunder/r/thunder_fw_radius_server"

  # accounting_interim_update - (optional) is a type of string
  accounting_interim_update = null
  # accounting_on - (optional) is a type of string
  accounting_on = null
  # accounting_start - (optional) is a type of string
  accounting_start = null
  # accounting_stop - (optional) is a type of string
  accounting_stop = null
  # attribute_name - (optional) is a type of string
  attribute_name = null
  # custom_attribute_name - (optional) is a type of string
  custom_attribute_name = null
  # encrypted - (optional) is a type of string
  encrypted = null
  # listen_port - (optional) is a type of number
  listen_port = null
  # secret - (optional) is a type of number
  secret = null
  # secret_string - (optional) is a type of string
  secret_string = null
  # uuid - (optional) is a type of string
  uuid = null
  # vrid - (optional) is a type of number
  vrid = null

  attribute = [{
    attribute_value = null
    custom_number   = null
    custom_vendor   = null
    name            = null
    number          = null
    prefix_length   = null
    prefix_number   = null
    prefix_vendor   = null
    value           = null
    vendor          = null
  }]

  remote = [{
    ip_list = [{
      ip_list_encrypted     = null
      ip_list_name          = null
      ip_list_secret        = null
      ip_list_secret_string = null
    }]
  }]

  sampling_enable = [{
    counters1 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accounting_interim_update" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "accounting_on" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "accounting_start" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "accounting_stop" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "attribute_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_attribute_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encrypted" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "listen_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "secret" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "secret_string" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "attribute" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      attribute_value = string
      custom_number   = number
      custom_vendor   = number
      name            = string
      number          = number
      prefix_length   = string
      prefix_number   = number
      prefix_vendor   = number
      value           = string
      vendor          = number
    }
  ))
  default = []
}

variable "remote" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ip_list = list(object(
        {
          ip_list_encrypted     = string
          ip_list_name          = string
          ip_list_secret        = number
          ip_list_secret_string = string
        }
      ))
    }
  ))
  default = []
}

variable "sampling_enable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      counters1 = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_fw_radius_server" "this" {
  accounting_interim_update = var.accounting_interim_update
  accounting_on             = var.accounting_on
  accounting_start          = var.accounting_start
  accounting_stop           = var.accounting_stop
  attribute_name            = var.attribute_name
  custom_attribute_name     = var.custom_attribute_name
  encrypted                 = var.encrypted
  listen_port               = var.listen_port
  secret                    = var.secret
  secret_string             = var.secret_string
  uuid                      = var.uuid
  vrid                      = var.vrid

  dynamic "attribute" {
    for_each = var.attribute
    content {
      attribute_value = attribute.value["attribute_value"]
      custom_number   = attribute.value["custom_number"]
      custom_vendor   = attribute.value["custom_vendor"]
      name            = attribute.value["name"]
      number          = attribute.value["number"]
      prefix_length   = attribute.value["prefix_length"]
      prefix_number   = attribute.value["prefix_number"]
      prefix_vendor   = attribute.value["prefix_vendor"]
      value           = attribute.value["value"]
      vendor          = attribute.value["vendor"]
    }
  }

  dynamic "remote" {
    for_each = var.remote
    content {

      dynamic "ip_list" {
        for_each = remote.value.ip_list
        content {
          ip_list_encrypted     = ip_list.value["ip_list_encrypted"]
          ip_list_name          = ip_list.value["ip_list_name"]
          ip_list_secret        = ip_list.value["ip_list_secret"]
          ip_list_secret_string = ip_list.value["ip_list_secret_string"]
        }
      }

    }
  }

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      counters1 = sampling_enable.value["counters1"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_radius_server.this.id
}

output "this" {
  value = thunder_fw_radius_server.this
}
```

[top](#index)