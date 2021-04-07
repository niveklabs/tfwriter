# fortios_wirelesscontroller_accesscontrollist

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
module "fortios_wirelesscontroller_accesscontrollist" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_accesscontrollist"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null

  layer3_ipv4_rules = [{
    action   = null
    comment  = null
    dstaddr  = null
    dstport  = null
    protocol = null
    rule_id  = null
    srcaddr  = null
    srcport  = null
  }]

  layer3_ipv6_rules = [{
    action   = null
    comment  = null
    dstaddr  = null
    dstport  = null
    protocol = null
    rule_id  = null
    srcaddr  = null
    srcport  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
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

variable "layer3_ipv4_rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action   = string
      comment  = string
      dstaddr  = string
      dstport  = number
      protocol = number
      rule_id  = number
      srcaddr  = string
      srcport  = number
    }
  ))
  default = []
}

variable "layer3_ipv6_rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action   = string
      comment  = string
      dstaddr  = string
      dstport  = number
      protocol = number
      rule_id  = number
      srcaddr  = string
      srcport  = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_accesscontrollist" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name

  dynamic "layer3_ipv4_rules" {
    for_each = var.layer3_ipv4_rules
    content {
      # action - (optional) is a type of string
      action = layer3_ipv4_rules.value["action"]
      # comment - (optional) is a type of string
      comment = layer3_ipv4_rules.value["comment"]
      # dstaddr - (optional) is a type of string
      dstaddr = layer3_ipv4_rules.value["dstaddr"]
      # dstport - (optional) is a type of number
      dstport = layer3_ipv4_rules.value["dstport"]
      # protocol - (optional) is a type of number
      protocol = layer3_ipv4_rules.value["protocol"]
      # rule_id - (optional) is a type of number
      rule_id = layer3_ipv4_rules.value["rule_id"]
      # srcaddr - (optional) is a type of string
      srcaddr = layer3_ipv4_rules.value["srcaddr"]
      # srcport - (optional) is a type of number
      srcport = layer3_ipv4_rules.value["srcport"]
    }
  }

  dynamic "layer3_ipv6_rules" {
    for_each = var.layer3_ipv6_rules
    content {
      # action - (optional) is a type of string
      action = layer3_ipv6_rules.value["action"]
      # comment - (optional) is a type of string
      comment = layer3_ipv6_rules.value["comment"]
      # dstaddr - (optional) is a type of string
      dstaddr = layer3_ipv6_rules.value["dstaddr"]
      # dstport - (optional) is a type of number
      dstport = layer3_ipv6_rules.value["dstport"]
      # protocol - (optional) is a type of number
      protocol = layer3_ipv6_rules.value["protocol"]
      # rule_id - (optional) is a type of number
      rule_id = layer3_ipv6_rules.value["rule_id"]
      # srcaddr - (optional) is a type of string
      srcaddr = layer3_ipv6_rules.value["srcaddr"]
      # srcport - (optional) is a type of number
      srcport = layer3_ipv6_rules.value["srcport"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "comment" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_accesscontrollist.this.comment
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_accesscontrollist.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_accesscontrollist.this.name
}

output "this" {
  value = fortios_wirelesscontroller_accesscontrollist.this
}
```

[top](#index)