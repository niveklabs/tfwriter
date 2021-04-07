# constellix_txt_record

[back](../constellix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "constellix_txt_record" {
  source = null

  # domain_id - (required) is a type of string
  domain_id = null
  # gtd_region - (optional) is a type of number
  gtd_region = null
  # name - (required) is a type of string
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
  # ttl - (optional) is a type of number
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
  description = "(required)"
  type        = string
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
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "roundrobin" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      disable_flag = bool
      value        = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "constellix_txt_record" "this" {
  # domain_id - (required) is a type of string
  domain_id = var.domain_id
  # gtd_region - (optional) is a type of number
  gtd_region = var.gtd_region
  # name - (required) is a type of string
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
  # ttl - (optional) is a type of number
  ttl = var.ttl
  # type - (optional) is a type of string
  type = var.type

  dynamic "roundrobin" {
    for_each = var.roundrobin
    content {
      # disable_flag - (optional) is a type of bool
      disable_flag = roundrobin.value["disable_flag"]
      # value - (required) is a type of string
      value = roundrobin.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "gtd_region" {
  description = "returns a number"
  value       = data.constellix_txt_record.this.gtd_region
}

output "id" {
  description = "returns a string"
  value       = data.constellix_txt_record.this.id
}

output "noanswer" {
  description = "returns a bool"
  value       = data.constellix_txt_record.this.noanswer
}

output "note" {
  description = "returns a string"
  value       = data.constellix_txt_record.this.note
}

output "parent" {
  description = "returns a string"
  value       = data.constellix_txt_record.this.parent
}

output "parentid" {
  description = "returns a number"
  value       = data.constellix_txt_record.this.parentid
}

output "source" {
  description = "returns a string"
  value       = data.constellix_txt_record.this.source
}

output "ttl" {
  description = "returns a number"
  value       = data.constellix_txt_record.this.ttl
}

output "type" {
  description = "returns a string"
  value       = data.constellix_txt_record.this.type
}

output "this" {
  value = constellix_txt_record.this
}
```

[top](#index)