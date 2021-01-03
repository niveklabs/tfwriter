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
    linode = ">= 1.13.4"
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
  # label - (optional) is a type of string
  label = null
  # linodes - (required) is a type of set of number
  linodes = []
  # tags - (optional) is a type of set of string
  tags = []

  inbound = [{
    addresses = []
    ports     = []
    protocol  = null
  }]

  outbound = [{
    addresses = []
    ports     = []
    protocol  = null
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

variable "label" {
  description = "(optional) - The label for the Firewall. For display purposes only. If no label is provided, a default will be assigned."
  type        = string
  default     = null
}

variable "linodes" {
  description = "(required) - The IDs of Linodes to apply this firewall to."
  type        = set(number)
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
      addresses = set(string)
      ports     = set(string)
      protocol  = string
    }
  ))
  default = []
}

variable "outbound" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      addresses = set(string)
      ports     = set(string)
      protocol  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "linode_firewall" "this" {
  disabled = var.disabled
  label    = var.label
  linodes  = var.linodes
  tags     = var.tags

  dynamic "inbound" {
    for_each = var.inbound
    content {
      addresses = inbound.value["addresses"]
      ports     = inbound.value["ports"]
      protocol  = inbound.value["protocol"]
    }
  }

  dynamic "outbound" {
    for_each = var.outbound
    content {
      addresses = outbound.value["addresses"]
      ports     = outbound.value["ports"]
      protocol  = outbound.value["protocol"]
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

output "label" {
  description = "returns a string"
  value       = linode_firewall.this.label
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