# nsxt_ip_pool

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
module "nsxt_ip_pool" {
  source = "./modules/nsxt/r/nsxt_ip_pool"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null

  subnet = [{
    allocation_ranges = []
    cidr              = null
    dns_nameservers   = []
    dns_suffix        = null
    gateway_ip        = null
  }]

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

variable "subnet" {
  description = "nested block: NestingList, min items: 0, max items: 5"
  type = set(object(
    {
      allocation_ranges = list(string)
      cidr              = string
      dns_nameservers   = list(string)
      dns_suffix        = string
      gateway_ip        = string
    }
  ))
  default = []
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
resource "nsxt_ip_pool" "this" {
  description  = var.description
  display_name = var.display_name

  dynamic "subnet" {
    for_each = var.subnet
    content {
      allocation_ranges = subnet.value["allocation_ranges"]
      cidr              = subnet.value["cidr"]
      dns_nameservers   = subnet.value["dns_nameservers"]
      dns_suffix        = subnet.value["dns_suffix"]
      gateway_ip        = subnet.value["gateway_ip"]
    }
  }

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
output "display_name" {
  description = "returns a string"
  value       = nsxt_ip_pool.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_ip_pool.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_ip_pool.this.revision
}

output "this" {
  value = nsxt_ip_pool.this
}
```

[top](#index)