# brightbox_firewall_rule

[back](../brightbox.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    brightbox = ">= 2.0.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "brightbox_firewall_rule" {
  source = null

  # description - (optional) is a type of string
  description = null
  # destination - (optional) is a type of string
  destination = null
  # destination_port - (optional) is a type of string
  destination_port = null
  # firewall_policy - (required) is a type of string
  firewall_policy = null
  # icmp_type_name - (optional) is a type of string
  icmp_type_name = null
  # protocol - (optional) is a type of string
  protocol = null
  # source - (optional) is a type of string
  # source_port - (optional) is a type of string
  source_port = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - User editable label"
  type        = string
  default     = null
}

variable "destination" {
  description = "(optional) - Subnet, ServerGroup or ServerID"
  type        = string
  default     = null
}

variable "destination_port" {
  description = "(optional) - single port, multiple ports or range separated by '-' or ':'; upto 255 characters example - '80', '80,443,21' or '3000-3999'"
  type        = string
  default     = null
}

variable "firewall_policy" {
  description = "(required) - The firewall policy this rule is linked to"
  type        = string
}

variable "icmp_type_name" {
  description = "(optional) - ICMP type name. 'echo-request', 'echo-reply'"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional) - Protocol Number, or one of tcp, udp, icmp"
  type        = string
  default     = null
}

variable "source" {
  description = "(optional) - Subnet, ServerGroup or ServerID"
  type        = string
  default     = null
}

variable "source_port" {
  description = "(optional) - single port, multiple ports or range separated by '-' or ':'; upto 255 characters example - '80', '80,443,21' or '3000-3999'"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "brightbox_firewall_rule" "this" {
  description      = var.description
  destination      = var.destination
  destination_port = var.destination_port
  firewall_policy  = var.firewall_policy
  icmp_type_name   = var.icmp_type_name
  protocol         = var.protocol
  source           = var.source
  source_port      = var.source_port

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = brightbox_firewall_rule.this.id
}

output "this" {
  value = brightbox_firewall_rule.this
}
```

[top](#index)