# nsxt_policy_service

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_service" {
  source = "./modules/nsxt/r/nsxt_policy_service"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # nsx_id - (optional) is a type of string
  nsx_id = null

  algorithm_entry = [{
    algorithm        = null
    description      = null
    destination_port = null
    display_name     = null
    source_ports     = []
  }]

  ether_type_entry = [{
    description  = null
    display_name = null
    ether_type   = null
  }]

  icmp_entry = [{
    description  = null
    display_name = null
    icmp_code    = null
    icmp_type    = null
    protocol     = null
  }]

  igmp_entry = [{
    description  = null
    display_name = null
  }]

  ip_protocol_entry = [{
    description  = null
    display_name = null
    protocol     = null
  }]

  l4_port_set_entry = [{
    description       = null
    destination_ports = []
    display_name      = null
    protocol          = null
    source_ports      = []
  }]

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "algorithm_entry" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      algorithm        = string
      description      = string
      destination_port = string
      display_name     = string
      source_ports     = set(string)
    }
  ))
  default = []
}

variable "ether_type_entry" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      description  = string
      display_name = string
      ether_type   = number
    }
  ))
  default = []
}

variable "icmp_entry" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      description  = string
      display_name = string
      icmp_code    = string
      icmp_type    = string
      protocol     = string
    }
  ))
  default = []
}

variable "igmp_entry" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      description  = string
      display_name = string
    }
  ))
  default = []
}

variable "ip_protocol_entry" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      description  = string
      display_name = string
      protocol     = number
    }
  ))
  default = []
}

variable "l4_port_set_entry" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      description       = string
      destination_ports = set(string)
      display_name      = string
      protocol          = string
      source_ports      = set(string)
    }
  ))
  default = []
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_policy_service" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # nsx_id - (optional) is a type of string
  nsx_id = var.nsx_id

  dynamic "algorithm_entry" {
    for_each = var.algorithm_entry
    content {
      # algorithm - (required) is a type of string
      algorithm = algorithm_entry.value["algorithm"]
      # description - (optional) is a type of string
      description = algorithm_entry.value["description"]
      # destination_port - (required) is a type of string
      destination_port = algorithm_entry.value["destination_port"]
      # display_name - (optional) is a type of string
      display_name = algorithm_entry.value["display_name"]
      # source_ports - (optional) is a type of set of string
      source_ports = algorithm_entry.value["source_ports"]
    }
  }

  dynamic "ether_type_entry" {
    for_each = var.ether_type_entry
    content {
      # description - (optional) is a type of string
      description = ether_type_entry.value["description"]
      # display_name - (optional) is a type of string
      display_name = ether_type_entry.value["display_name"]
      # ether_type - (required) is a type of number
      ether_type = ether_type_entry.value["ether_type"]
    }
  }

  dynamic "icmp_entry" {
    for_each = var.icmp_entry
    content {
      # description - (optional) is a type of string
      description = icmp_entry.value["description"]
      # display_name - (optional) is a type of string
      display_name = icmp_entry.value["display_name"]
      # icmp_code - (optional) is a type of string
      icmp_code = icmp_entry.value["icmp_code"]
      # icmp_type - (optional) is a type of string
      icmp_type = icmp_entry.value["icmp_type"]
      # protocol - (required) is a type of string
      protocol = icmp_entry.value["protocol"]
    }
  }

  dynamic "igmp_entry" {
    for_each = var.igmp_entry
    content {
      # description - (optional) is a type of string
      description = igmp_entry.value["description"]
      # display_name - (optional) is a type of string
      display_name = igmp_entry.value["display_name"]
    }
  }

  dynamic "ip_protocol_entry" {
    for_each = var.ip_protocol_entry
    content {
      # description - (optional) is a type of string
      description = ip_protocol_entry.value["description"]
      # display_name - (optional) is a type of string
      display_name = ip_protocol_entry.value["display_name"]
      # protocol - (required) is a type of number
      protocol = ip_protocol_entry.value["protocol"]
    }
  }

  dynamic "l4_port_set_entry" {
    for_each = var.l4_port_set_entry
    content {
      # description - (optional) is a type of string
      description = l4_port_set_entry.value["description"]
      # destination_ports - (optional) is a type of set of string
      destination_ports = l4_port_set_entry.value["destination_ports"]
      # display_name - (optional) is a type of string
      display_name = l4_port_set_entry.value["display_name"]
      # protocol - (required) is a type of string
      protocol = l4_port_set_entry.value["protocol"]
      # source_ports - (optional) is a type of set of string
      source_ports = l4_port_set_entry.value["source_ports"]
    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      # scope - (optional) is a type of string
      scope = tag.value["scope"]
      # tag - (optional) is a type of string
      tag = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nsxt_policy_service.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_service.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_service.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_service.this.revision
}

output "this" {
  value = nsxt_policy_service.this
}
```

[top](#index)