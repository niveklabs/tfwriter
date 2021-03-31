# constellix_ns_record

[back](../constellix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    constellix = ">= 0.3.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "constellix_ns_record" {
  source = "./modules/constellix/r/constellix_ns_record"

  # domain_id - (required) is a type of string
  domain_id = null
  # gtd_region - (optional) is a type of number
  gtd_region = null
  # name - (optional) is a type of string
  name = null
  # noanswer - (optional) is a type of bool
  noanswer = null
  # note - (optional) is a type of string
  note = null
  # source_type - (required) is a type of string
  source_type = null
  # ttl - (required) is a type of number
  ttl = null
  # type - (optional) is a type of string
  type = null

  roundrobin = [{
    disable_flag = null
    value        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain_id" {
  description = "(required)"
  type        = string
}

variable "gtd_region" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "noanswer" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "note" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_type" {
  description = "(required)"
  type        = string
}

variable "ttl" {
  description = "(required)"
  type        = number
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "roundrobin" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      disable_flag = string
      value        = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "constellix_ns_record" "this" {
  domain_id   = var.domain_id
  gtd_region  = var.gtd_region
  name        = var.name
  noanswer    = var.noanswer
  note        = var.note
  source_type = var.source_type
  ttl         = var.ttl
  type        = var.type

  dynamic "roundrobin" {
    for_each = var.roundrobin
    content {
      disable_flag = roundrobin.value["disable_flag"]
      value        = roundrobin.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "gtd_region" {
  description = "returns a number"
  value       = constellix_ns_record.this.gtd_region
}

output "id" {
  description = "returns a string"
  value       = constellix_ns_record.this.id
}

output "name" {
  description = "returns a string"
  value       = constellix_ns_record.this.name
}

output "noanswer" {
  description = "returns a bool"
  value       = constellix_ns_record.this.noanswer
}

output "note" {
  description = "returns a string"
  value       = constellix_ns_record.this.note
}

output "type" {
  description = "returns a string"
  value       = constellix_ns_record.this.type
}

output "this" {
  value = constellix_ns_record.this
}
```

[top](#index)