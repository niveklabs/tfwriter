# fortios_wirelesscontrollerhotspot20_h2qposuprovider

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
module "fortios_wirelesscontrollerhotspot20_h2qposuprovider" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_h2qposuprovider"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # icon - (optional) is a type of string
  icon = null
  # name - (optional) is a type of string
  name = null
  # osu_method - (optional) is a type of string
  osu_method = null
  # osu_nai - (optional) is a type of string
  osu_nai = null
  # server_uri - (optional) is a type of string
  server_uri = null

  friendly_name = [{
    friendly_name = null
    index         = null
    lang          = null
  }]

  service_description = [{
    lang                = null
    service_description = null
    service_id          = null
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

variable "icon" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "osu_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "osu_nai" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "friendly_name" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      friendly_name = string
      index         = number
      lang          = string
    }
  ))
  default = []
}

variable "service_description" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      lang                = string
      service_description = string
      service_id          = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontrollerhotspot20_h2qposuprovider" "this" {
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # icon - (optional) is a type of string
  icon = var.icon
  # name - (optional) is a type of string
  name = var.name
  # osu_method - (optional) is a type of string
  osu_method = var.osu_method
  # osu_nai - (optional) is a type of string
  osu_nai = var.osu_nai
  # server_uri - (optional) is a type of string
  server_uri = var.server_uri

  dynamic "friendly_name" {
    for_each = var.friendly_name
    content {
      # friendly_name - (optional) is a type of string
      friendly_name = friendly_name.value["friendly_name"]
      # index - (optional) is a type of number
      index = friendly_name.value["index"]
      # lang - (optional) is a type of string
      lang = friendly_name.value["lang"]
    }
  }

  dynamic "service_description" {
    for_each = var.service_description
    content {
      # lang - (optional) is a type of string
      lang = service_description.value["lang"]
      # service_description - (optional) is a type of string
      service_description = service_description.value["service_description"]
      # service_id - (optional) is a type of number
      service_id = service_description.value["service_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "icon" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qposuprovider.this.icon
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qposuprovider.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qposuprovider.this.name
}

output "osu_method" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qposuprovider.this.osu_method
}

output "osu_nai" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qposuprovider.this.osu_nai
}

output "server_uri" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qposuprovider.this.server_uri
}

output "this" {
  value = fortios_wirelesscontrollerhotspot20_h2qposuprovider.this
}
```

[top](#index)