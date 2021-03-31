# nsxt_policy_dns_forwarder_zone

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
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_dns_forwarder_zone" {
  source = "./modules/nsxt/r/nsxt_policy_dns_forwarder_zone"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # dns_domain_names - (optional) is a type of list of string
  dns_domain_names = []
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # upstream_servers - (required) is a type of list of string
  upstream_servers = []

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
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "dns_domain_names" {
  description = "(optional) - Domain names"
  type        = list(string)
  default     = null
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional) - The source IP used by the DNS Forwarder zone"
  type        = string
  default     = null
}

variable "upstream_servers" {
  description = "(required) - DNS servers to which the DNS request needs to be forwarded"
  type        = list(string)
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
resource "nsxt_policy_dns_forwarder_zone" "this" {
  description      = var.description
  display_name     = var.display_name
  dns_domain_names = var.dns_domain_names
  nsx_id           = var.nsx_id
  source_ip        = var.source_ip
  upstream_servers = var.upstream_servers

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
output "id" {
  description = "returns a string"
  value       = nsxt_policy_dns_forwarder_zone.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_dns_forwarder_zone.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_dns_forwarder_zone.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_dns_forwarder_zone.this.revision
}

output "this" {
  value = nsxt_policy_dns_forwarder_zone.this
}
```

[top](#index)