# oci_core_network_security_group_security_rule

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_network_security_group_security_rule" {
  source = null

  # description - (optional) is a type of string
  description = null
  # destination - (optional) is a type of string
  destination = null
  # destination_type - (optional) is a type of string
  destination_type = null
  # direction - (required) is a type of string
  direction = null
  # network_security_group_id - (required) is a type of string
  network_security_group_id = null
  # protocol - (required) is a type of string
  protocol = null
  # source - (optional) is a type of string
  # source_type - (optional) is a type of string
  source_type = null
  # stateless - (optional) is a type of bool
  stateless = null

  icmp_options = [{
    code = null
    type = null
  }]

  tcp_options = [{
    destination_port_range = [{
      max = null
      min = null
    }]
    source_port_range = [{
      max = null
      min = null
    }]
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  udp_options = [{
    destination_port_range = [{
      max = null
      min = null
    }]
    source_port_range = [{
      max = null
      min = null
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

variable "destination" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "direction" {
  description = "(required)"
  type        = string
}

variable "network_security_group_id" {
  description = "(required)"
  type        = string
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stateless" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "icmp_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      code = number
      type = number
    }
  ))
  default = []
}

variable "tcp_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      destination_port_range = list(object(
        {
          max = number
          min = number
        }
      ))
      source_port_range = list(object(
        {
          max = number
          min = number
        }
      ))
    }
  ))
  default = []
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

variable "udp_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      destination_port_range = list(object(
        {
          max = number
          min = number
        }
      ))
      source_port_range = list(object(
        {
          max = number
          min = number
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
resource "oci_core_network_security_group_security_rule" "this" {
  description               = var.description
  destination               = var.destination
  destination_type          = var.destination_type
  direction                 = var.direction
  network_security_group_id = var.network_security_group_id
  protocol                  = var.protocol
  source                    = var.source
  source_type               = var.source_type
  stateless                 = var.stateless

  dynamic "icmp_options" {
    for_each = var.icmp_options
    content {
      code = icmp_options.value["code"]
      type = icmp_options.value["type"]
    }
  }

  dynamic "tcp_options" {
    for_each = var.tcp_options
    content {

      dynamic "destination_port_range" {
        for_each = tcp_options.value.destination_port_range
        content {
          max = destination_port_range.value["max"]
          min = destination_port_range.value["min"]
        }
      }

      dynamic "source_port_range" {
        for_each = tcp_options.value.source_port_range
        content {
          max = source_port_range.value["max"]
          min = source_port_range.value["min"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

  dynamic "udp_options" {
    for_each = var.udp_options
    content {

      dynamic "destination_port_range" {
        for_each = udp_options.value.destination_port_range
        content {
          max = destination_port_range.value["max"]
          min = destination_port_range.value["min"]
        }
      }

      dynamic "source_port_range" {
        for_each = udp_options.value.source_port_range
        content {
          max = source_port_range.value["max"]
          min = source_port_range.value["min"]
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
  value       = oci_core_network_security_group_security_rule.this.description
}

output "destination" {
  description = "returns a string"
  value       = oci_core_network_security_group_security_rule.this.destination
}

output "destination_type" {
  description = "returns a string"
  value       = oci_core_network_security_group_security_rule.this.destination_type
}

output "id" {
  description = "returns a string"
  value       = oci_core_network_security_group_security_rule.this.id
}

output "is_valid" {
  description = "returns a bool"
  value       = oci_core_network_security_group_security_rule.this.is_valid
}

output "source_type" {
  description = "returns a string"
  value       = oci_core_network_security_group_security_rule.this.source_type
}

output "stateless" {
  description = "returns a bool"
  value       = oci_core_network_security_group_security_rule.this.stateless
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_network_security_group_security_rule.this.time_created
}

output "this" {
  value = oci_core_network_security_group_security_rule.this
}
```

[top](#index)