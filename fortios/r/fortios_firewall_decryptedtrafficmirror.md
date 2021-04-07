# fortios_firewall_decryptedtrafficmirror

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
module "fortios_firewall_decryptedtrafficmirror" {
  source = "./modules/fortios/r/fortios_firewall_decryptedtrafficmirror"

  # dstmac - (optional) is a type of string
  dstmac = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null
  # traffic_source - (optional) is a type of string
  traffic_source = null
  # traffic_type - (optional) is a type of string
  traffic_type = null

  interface = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dstmac" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "traffic_source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_decryptedtrafficmirror" "this" {
  # dstmac - (optional) is a type of string
  dstmac = var.dstmac
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name
  # traffic_source - (optional) is a type of string
  traffic_source = var.traffic_source
  # traffic_type - (optional) is a type of string
  traffic_type = var.traffic_type

  dynamic "interface" {
    for_each = var.interface
    content {
      # name - (optional) is a type of string
      name = interface.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "dstmac" {
  description = "returns a string"
  value       = fortios_firewall_decryptedtrafficmirror.this.dstmac
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_decryptedtrafficmirror.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_decryptedtrafficmirror.this.name
}

output "traffic_source" {
  description = "returns a string"
  value       = fortios_firewall_decryptedtrafficmirror.this.traffic_source
}

output "traffic_type" {
  description = "returns a string"
  value       = fortios_firewall_decryptedtrafficmirror.this.traffic_type
}

output "this" {
  value = fortios_firewall_decryptedtrafficmirror.this
}
```

[top](#index)