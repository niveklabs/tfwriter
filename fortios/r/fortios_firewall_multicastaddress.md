# fortios_firewall_multicastaddress

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
module "fortios_firewall_multicastaddress" {
  source = "./modules/fortios/r/fortios_firewall_multicastaddress"

  # associated_interface - (optional) is a type of string
  associated_interface = null
  # color - (optional) is a type of number
  color = null
  # comment - (optional) is a type of string
  comment = null
  # end_ip - (required) is a type of string
  end_ip = null
  # name - (optional) is a type of string
  name = null
  # start_ip - (required) is a type of string
  start_ip = null
  # subnet - (optional) is a type of string
  subnet = null
  # type - (optional) is a type of string
  type = null
  # visibility - (optional) is a type of string
  visibility = null

  tagging = [{
    category = null
    name     = null
    tags = [{
      name = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "associated_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "color" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_ip" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_ip" {
  description = "(required)"
  type        = string
}

variable "subnet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "visibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tagging" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      category = string
      name     = string
      tags = list(object(
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
resource "fortios_firewall_multicastaddress" "this" {
  associated_interface = var.associated_interface
  color                = var.color
  comment              = var.comment
  end_ip               = var.end_ip
  name                 = var.name
  start_ip             = var.start_ip
  subnet               = var.subnet
  type                 = var.type
  visibility           = var.visibility

  dynamic "tagging" {
    for_each = var.tagging
    content {
      category = tagging.value["category"]
      name     = tagging.value["name"]

      dynamic "tags" {
        for_each = tagging.value.tags
        content {
          name = tags.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "associated_interface" {
  description = "returns a string"
  value       = fortios_firewall_multicastaddress.this.associated_interface
}

output "color" {
  description = "returns a number"
  value       = fortios_firewall_multicastaddress.this.color
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_multicastaddress.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_multicastaddress.this.name
}

output "subnet" {
  description = "returns a string"
  value       = fortios_firewall_multicastaddress.this.subnet
}

output "type" {
  description = "returns a string"
  value       = fortios_firewall_multicastaddress.this.type
}

output "visibility" {
  description = "returns a string"
  value       = fortios_firewall_multicastaddress.this.visibility
}

output "this" {
  value = fortios_firewall_multicastaddress.this
}
```

[top](#index)