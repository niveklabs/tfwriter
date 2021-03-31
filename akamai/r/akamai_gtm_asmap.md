# akamai_gtm_asmap

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
module "akamai_gtm_asmap" {
  source = "./modules/akamai/r/akamai_gtm_asmap"

  # default_datacenter - (required) is a type of list of object
  default_datacenter = [{
    datacenter_id = null
    nickname      = null
  }]
  # domain - (required) is a type of string
  domain = null
  # name - (required) is a type of string
  name = null
  # wait_on_complete - (optional) is a type of bool
  wait_on_complete = null

  assignment = [{
    as_numbers    = []
    datacenter_id = null
    nickname      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_datacenter" {
  description = "(required)"
  type = list(object(
    {
      datacenter_id = number
      nickname      = string
    }
  ))
}

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
      as_numbers    = list(number)
      datacenter_id = number
      nickname      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "akamai_gtm_asmap" "this" {
  default_datacenter = var.default_datacenter
  domain             = var.domain
  name               = var.name
  wait_on_complete   = var.wait_on_complete

  dynamic "assignment" {
    for_each = var.assignment
    content {
      as_numbers    = assignment.value["as_numbers"]
      datacenter_id = assignment.value["datacenter_id"]
      nickname      = assignment.value["nickname"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_gtm_asmap.this.id
}

output "this" {
  value = akamai_gtm_asmap.this
}
```

[top](#index)