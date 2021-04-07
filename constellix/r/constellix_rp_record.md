# constellix_rp_record

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
module "constellix_rp_record" {
  source = null

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
  # parent - (optional) is a type of string
  parent = null
  # parentid - (optional) is a type of number
  parentid = null
  # source - (optional) is a type of string
  # source_type - (required) is a type of string
  source_type = null
  # ttl - (required) is a type of number
  ttl = null
  # type - (optional) is a type of string
  type = null

  roundrobin = [{
    disable_flag = null
    mailbox      = null
    txt          = null
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

variable "parent" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parentid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "source" {
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
      mailbox      = string
      txt          = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "constellix_rp_record" "this" {
  # domain_id - (required) is a type of string
  domain_id = var.domain_id
  # gtd_region - (optional) is a type of number
  gtd_region = var.gtd_region
  # name - (optional) is a type of string
  name = var.name
  # noanswer - (optional) is a type of bool
  noanswer = var.noanswer
  # note - (optional) is a type of string
  note = var.note
  # parent - (optional) is a type of string
  parent = var.parent
  # parentid - (optional) is a type of number
  parentid = var.parentid
  # source - (optional) is a type of string
  source = var.source
  # source_type - (required) is a type of string
  source_type = var.source_type
  # ttl - (required) is a type of number
  ttl = var.ttl
  # type - (optional) is a type of string
  type = var.type

  dynamic "roundrobin" {
    for_each = var.roundrobin
    content {
      # disable_flag - (optional) is a type of string
      disable_flag = roundrobin.value["disable_flag"]
      # mailbox - (required) is a type of string
      mailbox = roundrobin.value["mailbox"]
      # txt - (required) is a type of string
      txt = roundrobin.value["txt"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "gtd_region" {
  description = "returns a number"
  value       = constellix_rp_record.this.gtd_region
}

output "id" {
  description = "returns a string"
  value       = constellix_rp_record.this.id
}

output "noanswer" {
  description = "returns a bool"
  value       = constellix_rp_record.this.noanswer
}

output "note" {
  description = "returns a string"
  value       = constellix_rp_record.this.note
}

output "parent" {
  description = "returns a string"
  value       = constellix_rp_record.this.parent
}

output "parentid" {
  description = "returns a number"
  value       = constellix_rp_record.this.parentid
}

output "source" {
  description = "returns a string"
  value       = constellix_rp_record.this.source
}

output "type" {
  description = "returns a string"
  value       = constellix_rp_record.this.type
}

output "this" {
  value = constellix_rp_record.this
}
```

[top](#index)