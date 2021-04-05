# scaleway_instance_security_group

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
module "scaleway_instance_security_group" {
  source = "./modules/scaleway/r/scaleway_instance_security_group"

  # description - (optional) is a type of string
  description = null
  # enable_default_security - (optional) is a type of bool
  enable_default_security = null
  # external_rules - (optional) is a type of bool
  external_rules = null
  # inbound_default_policy - (optional) is a type of string
  inbound_default_policy = null
  # name - (optional) is a type of string
  name = null
  # outbound_default_policy - (optional) is a type of string
  outbound_default_policy = null
  # project_id - (optional) is a type of string
  project_id = null
  # stateful - (optional) is a type of bool
  stateful = null
  # zone - (optional) is a type of string
  zone = null

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
variable "description" {
  description = "(optional) - The description of the security group"
  type        = string
  default     = null
}

variable "enable_default_security" {
  description = "(optional) - Enable blocking of SMTP on IPv4 and IPv6"
  type        = bool
  default     = null
}

variable "external_rules" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "inbound_default_policy" {
  description = "(optional) - Default inbound traffic policy for this security group"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The name of the security group"
  type        = string
  default     = null
}

variable "outbound_default_policy" {
  description = "(optional) - Default outbound traffic policy for this security group"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "stateful" {
  description = "(optional) - The stateful value of the security group"
  type        = bool
  default     = null
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
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
resource "scaleway_instance_security_group" "this" {
  description             = var.description
  enable_default_security = var.enable_default_security
  external_rules          = var.external_rules
  inbound_default_policy  = var.inbound_default_policy
  name                    = var.name
  outbound_default_policy = var.outbound_default_policy
  project_id              = var.project_id
  stateful                = var.stateful
  zone                    = var.zone

  dynamic "inbound_rule" {
    for_each = var.inbound_rule
    content {
      action     = inbound_rule.value["action"]
      ip         = inbound_rule.value["ip"]
      ip_range   = inbound_rule.value["ip_range"]
      port       = inbound_rule.value["port"]
      port_range = inbound_rule.value["port_range"]
      protocol   = inbound_rule.value["protocol"]
    }
  }

  dynamic "outbound_rule" {
    for_each = var.outbound_rule
    content {
      action     = outbound_rule.value["action"]
      ip         = outbound_rule.value["ip"]
      ip_range   = outbound_rule.value["ip_range"]
      port       = outbound_rule.value["port"]
      port_range = outbound_rule.value["port_range"]
      protocol   = outbound_rule.value["protocol"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
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
  value       = scaleway_instance_security_group.this.id
}

output "name" {
  description = "returns a string"
  value       = scaleway_instance_security_group.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_instance_security_group.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_instance_security_group.this.project_id
}

output "zone" {
  description = "returns a string"
  value       = scaleway_instance_security_group.this.zone
}

output "this" {
  value = scaleway_instance_security_group.this
}
```

[top](#index)