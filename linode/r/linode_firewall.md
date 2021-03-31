# linode_firewall

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_firewall" {
  source = "./modules/linode/r/linode_firewall"

  # disabled - (optional) is a type of bool
  disabled = null
  # inbound_policy - (required) is a type of string
  inbound_policy = null
  # label - (required) is a type of string
  label = null
  # linodes - (optional) is a type of set of number
  linodes = []
  # outbound_policy - (required) is a type of string
  outbound_policy = null
  # tags - (optional) is a type of set of string
  tags = []

  inbound = [{
    action   = null
    ipv4     = []
    ipv6     = []
    label    = null
    ports    = null
    protocol = null
  }]

  outbound = [{
    action   = null
    ipv4     = []
    ipv6     = []
    label    = null
    ports    = null
    protocol = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "disabled" {
  description = "(optional) - If true, the Firewall is inactive."
  type        = bool
  default     = null
}

variable "inbound_policy" {
  description = "(required) - The default behavior for inbound traffic. This setting can be overridden by updating the inbound.action property for an individual Firewall Rule."
  type        = string
}

variable "label" {
  description = "(required) - The label for the Firewall. For display purposes only. If no label is provided, a default will be assigned."
  type        = string
}

variable "linodes" {
  description = "(optional) - The IDs of Linodes to apply this firewall to."
  type        = set(number)
  default     = null
}

variable "outbound_policy" {
  description = "(required) - The default behavior for outbound traffic. This setting can be overridden by updating the outbound.action property for an individual Firewall Rule."
  type        = string
}

variable "tags" {
  description = "(optional) - An array of tags applied to this object. Tags are for organizational purposes only."
  type        = set(string)
  default     = null
}

variable "inbound" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action   = string
      ipv4     = list(string)
      ipv6     = list(string)
      label    = string
      ports    = string
      protocol = string
    }
  ))
  default = []
}

variable "outbound" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action   = string
      ipv4     = list(string)
      ipv6     = list(string)
      label    = string
      ports    = string
      protocol = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "linode_firewall" "this" {
  disabled        = var.disabled
  inbound_policy  = var.inbound_policy
  label           = var.label
  linodes         = var.linodes
  outbound_policy = var.outbound_policy
  tags            = var.tags

  dynamic "inbound" {
    for_each = var.inbound
    content {
      action   = inbound.value["action"]
      ipv4     = inbound.value["ipv4"]
      ipv6     = inbound.value["ipv6"]
      label    = inbound.value["label"]
      ports    = inbound.value["ports"]
      protocol = inbound.value["protocol"]
    }
  }

  dynamic "outbound" {
    for_each = var.outbound
    content {
      action   = outbound.value["action"]
      ipv4     = outbound.value["ipv4"]
      ipv6     = outbound.value["ipv6"]
      label    = outbound.value["label"]
      ports    = outbound.value["ports"]
      protocol = outbound.value["protocol"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "devices" {
  description = "returns a list of object"
  value       = linode_firewall.this.devices
}

output "id" {
  description = "returns a string"
  value       = linode_firewall.this.id
}

output "status" {
  description = "returns a string"
  value       = linode_firewall.this.status
}

output "this" {
  value = linode_firewall.this
}
```

[top](#index)