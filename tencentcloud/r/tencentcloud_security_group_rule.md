# tencentcloud_security_group_rule

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_security_group_rule" {
  source = "./modules/tencentcloud/r/tencentcloud_security_group_rule"

  # cidr_ip - (optional) is a type of string
  cidr_ip = null
  # description - (optional) is a type of string
  description = null
  # ip_protocol - (optional) is a type of string
  ip_protocol = null
  # policy - (required) is a type of string
  policy = null
  # port_range - (optional) is a type of string
  port_range = null
  # security_group_id - (required) is a type of string
  security_group_id = null
  # source_sgid - (optional) is a type of string
  source_sgid = null
  # type - (required) is a type of string
  type = null

  address_template = [{
    group_id    = null
    template_id = null
  }]

  protocol_template = [{
    group_id    = null
    template_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cidr_ip" {
  description = "(optional) - An IP address network or segment, and conflict with `source_sgid` and `address_template`."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description of the security group rule."
  type        = string
  default     = null
}

variable "ip_protocol" {
  description = "(optional) - Type of IP protocol. Valid values: `TCP`, `UDP` and `ICMP`. Default to all types protocol, and conflicts with `protocol_template`."
  type        = string
  default     = null
}

variable "policy" {
  description = "(required) - Rule policy of security group. Valid values: `ACCEPT` and `DROP`."
  type        = string
}

variable "port_range" {
  description = "(optional) - Range of the port. The available value can be one, multiple or one segment. E.g. `80`, `80,90` and `80-90`. Default to all ports, and confilicts with `protocol_template`."
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(required) - ID of the security group to be queried."
  type        = string
}

variable "source_sgid" {
  description = "(optional) - ID of the nested security group, and conflicts with `cidr_ip` and `address_template`."
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - Type of the security group rule. Valid values: `ingress` and `egress`."
  type        = string
}

variable "address_template" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      group_id    = string
      template_id = string
    }
  ))
  default = []
}

variable "protocol_template" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      group_id    = string
      template_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_security_group_rule" "this" {
  cidr_ip           = var.cidr_ip
  description       = var.description
  ip_protocol       = var.ip_protocol
  policy            = var.policy
  port_range        = var.port_range
  security_group_id = var.security_group_id
  source_sgid       = var.source_sgid
  type              = var.type

  dynamic "address_template" {
    for_each = var.address_template
    content {
      group_id    = address_template.value["group_id"]
      template_id = address_template.value["template_id"]
    }
  }

  dynamic "protocol_template" {
    for_each = var.protocol_template
    content {
      group_id    = protocol_template.value["group_id"]
      template_id = protocol_template.value["template_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = tencentcloud_security_group_rule.this.description
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_security_group_rule.this.id
}

output "ip_protocol" {
  description = "returns a string"
  value       = tencentcloud_security_group_rule.this.ip_protocol
}

output "port_range" {
  description = "returns a string"
  value       = tencentcloud_security_group_rule.this.port_range
}

output "source_sgid" {
  description = "returns a string"
  value       = tencentcloud_security_group_rule.this.source_sgid
}

output "this" {
  value = tencentcloud_security_group_rule.this
}
```

[top](#index)