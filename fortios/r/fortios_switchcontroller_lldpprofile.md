# fortios_switchcontroller_lldpprofile

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
module "fortios_switchcontroller_lldpprofile" {
  source = "./modules/fortios/r/fortios_switchcontroller_lldpprofile"

  # auto_isl - (optional) is a type of string
  auto_isl = null
  # auto_isl_hello_timer - (optional) is a type of number
  auto_isl_hello_timer = null
  # auto_isl_port_group - (optional) is a type of number
  auto_isl_port_group = null
  # auto_isl_receive_timeout - (optional) is a type of number
  auto_isl_receive_timeout = null
  # med_tlvs - (optional) is a type of string
  med_tlvs = null
  # n8021_tlvs - (optional) is a type of string
  n8021_tlvs = null
  # n8023_tlvs - (optional) is a type of string
  n8023_tlvs = null
  # name - (optional) is a type of string
  name = null

  custom_tlvs = [{
    information_string = null
    name               = null
    oui                = null
    subtype            = null
  }]

  med_network_policy = [{
    dscp     = null
    name     = null
    priority = null
    status   = null
    vlan     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_isl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_isl_hello_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto_isl_port_group" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto_isl_receive_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "med_tlvs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "n8021_tlvs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "n8023_tlvs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_tlvs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      information_string = string
      name               = string
      oui                = string
      subtype            = number
    }
  ))
  default = []
}

variable "med_network_policy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      dscp     = number
      name     = string
      priority = number
      status   = string
      vlan     = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_lldpprofile" "this" {
  auto_isl                 = var.auto_isl
  auto_isl_hello_timer     = var.auto_isl_hello_timer
  auto_isl_port_group      = var.auto_isl_port_group
  auto_isl_receive_timeout = var.auto_isl_receive_timeout
  med_tlvs                 = var.med_tlvs
  n8021_tlvs               = var.n8021_tlvs
  n8023_tlvs               = var.n8023_tlvs
  name                     = var.name

  dynamic "custom_tlvs" {
    for_each = var.custom_tlvs
    content {
      information_string = custom_tlvs.value["information_string"]
      name               = custom_tlvs.value["name"]
      oui                = custom_tlvs.value["oui"]
      subtype            = custom_tlvs.value["subtype"]
    }
  }

  dynamic "med_network_policy" {
    for_each = var.med_network_policy
    content {
      dscp     = med_network_policy.value["dscp"]
      name     = med_network_policy.value["name"]
      priority = med_network_policy.value["priority"]
      status   = med_network_policy.value["status"]
      vlan     = med_network_policy.value["vlan"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auto_isl" {
  description = "returns a string"
  value       = fortios_switchcontroller_lldpprofile.this.auto_isl
}

output "auto_isl_hello_timer" {
  description = "returns a number"
  value       = fortios_switchcontroller_lldpprofile.this.auto_isl_hello_timer
}

output "auto_isl_port_group" {
  description = "returns a number"
  value       = fortios_switchcontroller_lldpprofile.this.auto_isl_port_group
}

output "auto_isl_receive_timeout" {
  description = "returns a number"
  value       = fortios_switchcontroller_lldpprofile.this.auto_isl_receive_timeout
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_lldpprofile.this.id
}

output "med_tlvs" {
  description = "returns a string"
  value       = fortios_switchcontroller_lldpprofile.this.med_tlvs
}

output "n8021_tlvs" {
  description = "returns a string"
  value       = fortios_switchcontroller_lldpprofile.this.n8021_tlvs
}

output "n8023_tlvs" {
  description = "returns a string"
  value       = fortios_switchcontroller_lldpprofile.this.n8023_tlvs
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_lldpprofile.this.name
}

output "this" {
  value = fortios_switchcontroller_lldpprofile.this
}
```

[top](#index)