# oci_core_security_list

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_security_list" {
  source = "./modules/oci/r/oci_core_security_list"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # vcn_id - (required) is a type of string
  vcn_id = null

  egress_security_rules = [{
    description      = null
    destination      = null
    destination_type = null
    icmp_options = [{
      code = null
      type = null
    }]
    protocol  = null
    stateless = null
    tcp_options = [{
      max = null
      min = null
      source_port_range = [{
        max = null
        min = null
      }]
    }]
    udp_options = [{
      max = null
      min = null
      source_port_range = [{
        max = null
        min = null
      }]
    }]
  }]

  ingress_security_rules = [{
    description = null
    icmp_options = [{
      code = null
      type = null
    }]
    protocol    = null
    source      = null
    source_type = null
    stateless   = null
    tcp_options = [{
      max = null
      min = null
      source_port_range = [{
        max = null
        min = null
      }]
    }]
    udp_options = [{
      max = null
      min = null
      source_port_range = [{
        max = null
        min = null
      }]
    }]
  }]

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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vcn_id" {
  description = "(required)"
  type        = string
}

variable "egress_security_rules" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      description      = string
      destination      = string
      destination_type = string
      icmp_options = list(object(
        {
          code = number
          type = number
        }
      ))
      protocol  = string
      stateless = bool
      tcp_options = list(object(
        {
          max = number
          min = number
          source_port_range = list(object(
            {
              max = number
              min = number
            }
          ))
        }
      ))
      udp_options = list(object(
        {
          max = number
          min = number
          source_port_range = list(object(
            {
              max = number
              min = number
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "ingress_security_rules" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      icmp_options = list(object(
        {
          code = number
          type = number
        }
      ))
      protocol    = string
      source      = string
      source_type = string
      stateless   = bool
      tcp_options = list(object(
        {
          max = number
          min = number
          source_port_range = list(object(
            {
              max = number
              min = number
            }
          ))
        }
      ))
      udp_options = list(object(
        {
          max = number
          min = number
          source_port_range = list(object(
            {
              max = number
              min = number
            }
          ))
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
```

[top](#index)

### Resource

```terraform
resource "oci_core_security_list" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # vcn_id - (required) is a type of string
  vcn_id = var.vcn_id

  dynamic "egress_security_rules" {
    for_each = var.egress_security_rules
    content {
      # description - (optional) is a type of string
      description = egress_security_rules.value["description"]
      # destination - (required) is a type of string
      destination = egress_security_rules.value["destination"]
      # destination_type - (optional) is a type of string
      destination_type = egress_security_rules.value["destination_type"]
      # protocol - (required) is a type of string
      protocol = egress_security_rules.value["protocol"]
      # stateless - (optional) is a type of bool
      stateless = egress_security_rules.value["stateless"]

      dynamic "icmp_options" {
        for_each = egress_security_rules.value.icmp_options
        content {
          # code - (optional) is a type of number
          code = icmp_options.value["code"]
          # type - (required) is a type of number
          type = icmp_options.value["type"]
        }
      }

      dynamic "tcp_options" {
        for_each = egress_security_rules.value.tcp_options
        content {
          # max - (optional) is a type of number
          max = tcp_options.value["max"]
          # min - (optional) is a type of number
          min = tcp_options.value["min"]

          dynamic "source_port_range" {
            for_each = tcp_options.value.source_port_range
            content {
              # max - (required) is a type of number
              max = source_port_range.value["max"]
              # min - (required) is a type of number
              min = source_port_range.value["min"]
            }
          }

        }
      }

      dynamic "udp_options" {
        for_each = egress_security_rules.value.udp_options
        content {
          # max - (optional) is a type of number
          max = udp_options.value["max"]
          # min - (optional) is a type of number
          min = udp_options.value["min"]

          dynamic "source_port_range" {
            for_each = udp_options.value.source_port_range
            content {
              # max - (required) is a type of number
              max = source_port_range.value["max"]
              # min - (required) is a type of number
              min = source_port_range.value["min"]
            }
          }

        }
      }

    }
  }

  dynamic "ingress_security_rules" {
    for_each = var.ingress_security_rules
    content {
      # description - (optional) is a type of string
      description = ingress_security_rules.value["description"]
      # protocol - (required) is a type of string
      protocol = ingress_security_rules.value["protocol"]
      # source - (required) is a type of string
      source = ingress_security_rules.value["source"]
      # source_type - (optional) is a type of string
      source_type = ingress_security_rules.value["source_type"]
      # stateless - (optional) is a type of bool
      stateless = ingress_security_rules.value["stateless"]

      dynamic "icmp_options" {
        for_each = ingress_security_rules.value.icmp_options
        content {
          # code - (optional) is a type of number
          code = icmp_options.value["code"]
          # type - (required) is a type of number
          type = icmp_options.value["type"]
        }
      }

      dynamic "tcp_options" {
        for_each = ingress_security_rules.value.tcp_options
        content {
          # max - (optional) is a type of number
          max = tcp_options.value["max"]
          # min - (optional) is a type of number
          min = tcp_options.value["min"]

          dynamic "source_port_range" {
            for_each = tcp_options.value.source_port_range
            content {
              # max - (required) is a type of number
              max = source_port_range.value["max"]
              # min - (required) is a type of number
              min = source_port_range.value["min"]
            }
          }

        }
      }

      dynamic "udp_options" {
        for_each = ingress_security_rules.value.udp_options
        content {
          # max - (optional) is a type of number
          max = udp_options.value["max"]
          # min - (optional) is a type of number
          min = udp_options.value["min"]

          dynamic "source_port_range" {
            for_each = udp_options.value.source_port_range
            content {
              # max - (required) is a type of number
              max = source_port_range.value["max"]
              # min - (required) is a type of number
              min = source_port_range.value["min"]
            }
          }

        }
      }

    }
  }

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_security_list.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_security_list.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_security_list.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_security_list.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_core_security_list.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_security_list.this.time_created
}

output "this" {
  value = oci_core_security_list.this
}
```

[top](#index)