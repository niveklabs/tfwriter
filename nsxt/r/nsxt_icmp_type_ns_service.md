# nsxt_icmp_type_ns_service

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
    nsxt = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_icmp_type_ns_service" {
  source = "./modules/nsxt/r/nsxt_icmp_type_ns_service"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # icmp_code - (optional) is a type of number
  icmp_code = null
  # icmp_type - (optional) is a type of number
  icmp_type = null
  # protocol - (required) is a type of string
  protocol = null

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
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "icmp_code" {
  description = "(optional) - ICMP message code"
  type        = number
  default     = null
}

variable "icmp_type" {
  description = "(optional) - ICMP message type"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(required) - Version of ICMP protocol (ICMPv4/ICMPv6)"
  type        = string
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
resource "nsxt_icmp_type_ns_service" "this" {
  description  = var.description
  display_name = var.display_name
  icmp_code    = var.icmp_code
  icmp_type    = var.icmp_type
  protocol     = var.protocol

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_service" {
  description = "returns a bool"
  value       = nsxt_icmp_type_ns_service.this.default_service
}

output "display_name" {
  description = "returns a string"
  value       = nsxt_icmp_type_ns_service.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_icmp_type_ns_service.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_icmp_type_ns_service.this.revision
}

output "this" {
  value = nsxt_icmp_type_ns_service.this
}
```

[top](#index)