# spotinst_multai_balancer

[back](../spotinst.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    spotinst = ">= 1.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "spotinst_multai_balancer" {
  source = "./modules/spotinst/r/spotinst_multai_balancer"

  # dns_cname_aliases - (optional) is a type of list of string
  dns_cname_aliases = []
  # name - (required) is a type of string
  name = null
  # scheme - (optional) is a type of string
  scheme = null

  connection_timeouts = [{
    draining = null
    idle     = null
  }]

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dns_cname_aliases" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "scheme" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "connection_timeouts" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      draining = number
      idle     = number
    }
  ))
  default = []
}

variable "tags" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "spotinst_multai_balancer" "this" {
  # dns_cname_aliases - (optional) is a type of list of string
  dns_cname_aliases = var.dns_cname_aliases
  # name - (required) is a type of string
  name = var.name
  # scheme - (optional) is a type of string
  scheme = var.scheme

  dynamic "connection_timeouts" {
    for_each = var.connection_timeouts
    content {
      # draining - (optional) is a type of number
      draining = connection_timeouts.value["draining"]
      # idle - (optional) is a type of number
      idle = connection_timeouts.value["idle"]
    }
  }

  dynamic "tags" {
    for_each = var.tags
    content {
      # key - (required) is a type of string
      key = tags.value["key"]
      # value - (required) is a type of string
      value = tags.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = spotinst_multai_balancer.this.id
}

output "this" {
  value = spotinst_multai_balancer.this
}
```

[top](#index)