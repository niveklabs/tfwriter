# scaleway_instance_security_group_rules

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_instance_security_group_rules" {
  source = "./modules/scaleway/r/scaleway_instance_security_group_rules"

  # security_group_id - (required) is a type of string
  security_group_id = null

  inbound_rule = [{
    action     = null
    ip         = null
    ip_range   = null
    port       = null
    port_range = null
    protocol   = null
  }]

  outbound_rule = [{
    action     = null
    ip         = null
    ip_range   = null
    port       = null
    port_range = null
    protocol   = null
  }]

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "security_group_id" {
  description = "(required) - The security group associated with this volume"
  type        = string
}

variable "inbound_rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action     = string
      ip         = string
      ip_range   = string
      port       = number
      port_range = string
      protocol   = string
    }
  ))
  default = []
}

variable "outbound_rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action     = string
      ip         = string
      ip_range   = string
      port       = number
      port_range = string
      protocol   = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_instance_security_group_rules" "this" {
  # security_group_id - (required) is a type of string
  security_group_id = var.security_group_id

  dynamic "inbound_rule" {
    for_each = var.inbound_rule
    content {
      # action - (required) is a type of string
      action = inbound_rule.value["action"]
      # ip - (optional) is a type of string
      ip = inbound_rule.value["ip"]
      # ip_range - (optional) is a type of string
      ip_range = inbound_rule.value["ip_range"]
      # port - (optional) is a type of number
      port = inbound_rule.value["port"]
      # port_range - (optional) is a type of string
      port_range = inbound_rule.value["port_range"]
      # protocol - (optional) is a type of string
      protocol = inbound_rule.value["protocol"]
    }
  }

  dynamic "outbound_rule" {
    for_each = var.outbound_rule
    content {
      # action - (required) is a type of string
      action = outbound_rule.value["action"]
      # ip - (optional) is a type of string
      ip = outbound_rule.value["ip"]
      # ip_range - (optional) is a type of string
      ip_range = outbound_rule.value["ip_range"]
      # port - (optional) is a type of number
      port = outbound_rule.value["port"]
      # port_range - (optional) is a type of string
      port_range = outbound_rule.value["port_range"]
      # protocol - (optional) is a type of string
      protocol = outbound_rule.value["protocol"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = scaleway_instance_security_group_rules.this.id
}

output "this" {
  value = scaleway_instance_security_group_rules.this
}
```

[top](#index)