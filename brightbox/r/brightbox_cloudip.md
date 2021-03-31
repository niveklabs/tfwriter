# brightbox_cloudip

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
module "brightbox_cloudip" {
  source = "./modules/brightbox/r/brightbox_cloudip"

  # name - (optional) is a type of string
  name = null
  # reverse_dns - (optional) is a type of string
  reverse_dns = null
  # target - (optional) is a type of string
  target = null

  port_translator = [{
    incoming = null
    outgoing = null
    protocol = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name assigned to the Cloud IP"
  type        = string
  default     = null
}

variable "reverse_dns" {
  description = "(optional) - Reverse DNS entry for the Cloud IP"
  type        = string
  default     = null
}

variable "target" {
  description = "(optional) - The object this Cloud IP maps to"
  type        = string
  default     = null
}

variable "port_translator" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      incoming = number
      outgoing = number
      protocol = string
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "brightbox_cloudip" "this" {
  name        = var.name
  reverse_dns = var.reverse_dns
  target      = var.target

  dynamic "port_translator" {
    for_each = var.port_translator
    content {
      incoming = port_translator.value["incoming"]
      outgoing = port_translator.value["outgoing"]
      protocol = port_translator.value["protocol"]
    }
  }

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
output "fqdn" {
  description = "returns a string"
  value       = brightbox_cloudip.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = brightbox_cloudip.this.id
}

output "locked" {
  description = "returns a string"
  value       = brightbox_cloudip.this.locked
}

output "public_ip" {
  description = "returns a string"
  value       = brightbox_cloudip.this.public_ip
}

output "public_ipv4" {
  description = "returns a string"
  value       = brightbox_cloudip.this.public_ipv4
}

output "public_ipv6" {
  description = "returns a string"
  value       = brightbox_cloudip.this.public_ipv6
}

output "reverse_dns" {
  description = "returns a string"
  value       = brightbox_cloudip.this.reverse_dns
}

output "status" {
  description = "returns a string"
  value       = brightbox_cloudip.this.status
}

output "this" {
  value = brightbox_cloudip.this
}
```

[top](#index)