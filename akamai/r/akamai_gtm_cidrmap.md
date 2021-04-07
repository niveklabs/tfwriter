# akamai_gtm_cidrmap

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_gtm_cidrmap" {
  source = "./modules/akamai/r/akamai_gtm_cidrmap"

  # domain - (required) is a type of string
  domain = null
  # name - (required) is a type of string
  name = null
  # wait_on_complete - (optional) is a type of bool
  wait_on_complete = null

  assignment = [{
    blocks        = []
    datacenter_id = null
    nickname      = null
  }]

  default_datacenter = [{
    datacenter_id = null
    nickname      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "wait_on_complete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "assignment" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      blocks        = list(string)
      datacenter_id = number
      nickname      = string
    }
  ))
  default = []
}

variable "default_datacenter" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      datacenter_id = number
      nickname      = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "akamai_gtm_cidrmap" "this" {
  # domain - (required) is a type of string
  domain = var.domain
  # name - (required) is a type of string
  name = var.name
  # wait_on_complete - (optional) is a type of bool
  wait_on_complete = var.wait_on_complete

  dynamic "assignment" {
    for_each = var.assignment
    content {
      # blocks - (optional) is a type of list of string
      blocks = assignment.value["blocks"]
      # datacenter_id - (required) is a type of number
      datacenter_id = assignment.value["datacenter_id"]
      # nickname - (required) is a type of string
      nickname = assignment.value["nickname"]
    }
  }

  dynamic "default_datacenter" {
    for_each = var.default_datacenter
    content {
      # datacenter_id - (required) is a type of number
      datacenter_id = default_datacenter.value["datacenter_id"]
      # nickname - (optional) is a type of string
      nickname = default_datacenter.value["nickname"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_gtm_cidrmap.this.id
}

output "this" {
  value = akamai_gtm_cidrmap.this
}
```

[top](#index)