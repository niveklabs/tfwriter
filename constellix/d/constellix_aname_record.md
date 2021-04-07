# constellix_aname_record

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
module "constellix_aname_record" {
  source = "./modules/constellix/d/constellix_aname_record"

  # contact_ids - (optional) is a type of list of number
  contact_ids = []
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
  # record_failover_disable_flag - (optional) is a type of string
  record_failover_disable_flag = null
  # record_failover_failover_type - (optional) is a type of number
  record_failover_failover_type = null
  # record_option - (optional) is a type of string
  record_option = null
  # source_type - (required) is a type of string
  source_type = null
  # ttl - (optional) is a type of number
  ttl = null
  # type - (optional) is a type of string
  type = null

  record_failover_values = [{
    checkidrcdf  = null
    disable_flag = null
    sort_order   = null
    value        = null
  }]

  roundrobin = [{
    disable_flag = null
    value        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "contact_ids" {
  description = "(optional)"
  type        = list(number)
  default     = null
}

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

variable "record_failover_disable_flag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "record_failover_failover_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "record_option" {
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

variable "record_failover_values" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      checkidrcdf  = string
      disable_flag = string
      sort_order   = string
      value        = string
    }
  ))
  default = []
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
data "constellix_aname_record" "this" {
  # contact_ids - (optional) is a type of list of number
  contact_ids = var.contact_ids
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
  # record_failover_disable_flag - (optional) is a type of string
  record_failover_disable_flag = var.record_failover_disable_flag
  # record_failover_failover_type - (optional) is a type of number
  record_failover_failover_type = var.record_failover_failover_type
  # record_option - (optional) is a type of string
  record_option = var.record_option
  # source_type - (required) is a type of string
  source_type = var.source_type
  # ttl - (optional) is a type of number
  ttl = var.ttl
  # type - (optional) is a type of string
  type = var.type

  dynamic "record_failover_values" {
    for_each = var.record_failover_values
    content {
      # checkidrcdf - (optional) is a type of string
      checkidrcdf = record_failover_values.value["checkidrcdf"]
      # disable_flag - (optional) is a type of string
      disable_flag = record_failover_values.value["disable_flag"]
      # sort_order - (optional) is a type of string
      sort_order = record_failover_values.value["sort_order"]
      # value - (optional) is a type of string
      value = record_failover_values.value["value"]
    }
  }

  dynamic "roundrobin" {
    for_each = var.roundrobin
    content {
      # disable_flag - (optional) is a type of bool
      disable_flag = roundrobin.value["disable_flag"]
      # value - (optional) is a type of string
      value = roundrobin.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "contact_ids" {
  description = "returns a list of number"
  value       = data.constellix_aname_record.this.contact_ids
}

output "gtd_region" {
  description = "returns a number"
  value       = data.constellix_aname_record.this.gtd_region
}

output "id" {
  description = "returns a string"
  value       = data.constellix_aname_record.this.id
}

output "noanswer" {
  description = "returns a bool"
  value       = data.constellix_aname_record.this.noanswer
}

output "note" {
  description = "returns a string"
  value       = data.constellix_aname_record.this.note
}

output "record_failover_disable_flag" {
  description = "returns a string"
  value       = data.constellix_aname_record.this.record_failover_disable_flag
}

output "record_failover_failover_type" {
  description = "returns a number"
  value       = data.constellix_aname_record.this.record_failover_failover_type
}

output "record_option" {
  description = "returns a string"
  value       = data.constellix_aname_record.this.record_option
}

output "ttl" {
  description = "returns a number"
  value       = data.constellix_aname_record.this.ttl
}

output "type" {
  description = "returns a string"
  value       = data.constellix_aname_record.this.type
}

output "this" {
  value = constellix_aname_record.this
}
```

[top](#index)