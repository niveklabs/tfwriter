# opennebula_security_group

[back](../opennebula.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opennebula = ">= 0.2.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opennebula_security_group" {
  source = "./modules/opennebula/r/opennebula_security_group"

  # commit - (optional) is a type of bool
  commit = null
  # description - (optional) is a type of string
  description = null
  # group - (optional) is a type of string
  group = null
  # name - (required) is a type of string
  name = null
  # permissions - (optional) is a type of string
  permissions = null
  # tags - (optional) is a type of map of string
  tags = {}

  rule = [{
    icmp_type  = null
    ip         = null
    network_id = null
    protocol   = null
    range      = null
    rule_type  = null
    size       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "commit" {
  description = "(optional) - Should changes to the Security Group rules be commited to running Virtual Machines?"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - Description of the Security Group Rule Set"
  type        = string
  default     = null
}

variable "group" {
  description = "(optional) - Name of the Group that onws the Security Group, If empty, it uses caller group"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the Security Group"
  type        = string
}

variable "permissions" {
  description = "(optional) - Permissions for the Security Group (in Unix format, owner-group-other, use-manage-admin)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Add custom tags to the resource"
  type        = map(string)
  default     = null
}

variable "rule" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      icmp_type  = string
      ip         = string
      network_id = string
      protocol   = string
      range      = string
      rule_type  = string
      size       = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "opennebula_security_group" "this" {
  # commit - (optional) is a type of bool
  commit = var.commit
  # description - (optional) is a type of string
  description = var.description
  # group - (optional) is a type of string
  group = var.group
  # name - (required) is a type of string
  name = var.name
  # permissions - (optional) is a type of string
  permissions = var.permissions
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "rule" {
    for_each = var.rule
    content {
      # icmp_type - (optional) is a type of string
      icmp_type = rule.value["icmp_type"]
      # ip - (optional) is a type of string
      ip = rule.value["ip"]
      # network_id - (optional) is a type of string
      network_id = rule.value["network_id"]
      # protocol - (required) is a type of string
      protocol = rule.value["protocol"]
      # range - (optional) is a type of string
      range = rule.value["range"]
      # rule_type - (required) is a type of string
      rule_type = rule.value["rule_type"]
      # size - (optional) is a type of string
      size = rule.value["size"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = opennebula_security_group.this.description
}

output "gid" {
  description = "returns a number"
  value       = opennebula_security_group.this.gid
}

output "gname" {
  description = "returns a string"
  value       = opennebula_security_group.this.gname
}

output "id" {
  description = "returns a string"
  value       = opennebula_security_group.this.id
}

output "permissions" {
  description = "returns a string"
  value       = opennebula_security_group.this.permissions
}

output "uid" {
  description = "returns a number"
  value       = opennebula_security_group.this.uid
}

output "uname" {
  description = "returns a string"
  value       = opennebula_security_group.this.uname
}

output "this" {
  value = opennebula_security_group.this
}
```

[top](#index)