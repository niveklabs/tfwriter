# constellix_cname_record

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
module "constellix_cname_record" {
  source = "./modules/constellix/d/constellix_cname_record"

  # contact_ids - (optional) is a type of list of number
  contact_ids = []
  # domain_id - (required) is a type of string
  domain_id = null
  # geo_location - (optional) is a type of map of string
  geo_location = {}
  # gtd_region - (optional) is a type of number
  gtd_region = null
  # host - (optional) is a type of string
  host = null
  # name - (required) is a type of string
  name = null
  # noanswer - (optional) is a type of bool
  noanswer = null
  # note - (optional) is a type of string
  note = null
  # pools - (optional) is a type of list of number
  pools = []
  # record_failover_disable_flag - (optional) is a type of string
  record_failover_disable_flag = null
  # record_failover_failover_type - (optional) is a type of string
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
    check_id     = null
    disable_flag = null
    sort_order   = null
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

variable "geo_location" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "gtd_region" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "host" {
  description = "(optional)"
  type        = string
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

variable "pools" {
  description = "(optional)"
  type        = list(number)
  default     = null
}

variable "record_failover_disable_flag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "record_failover_failover_type" {
  description = "(optional)"
  type        = string
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
      check_id     = number
      disable_flag = string
      sort_order   = string
      value        = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "constellix_cname_record" "this" {
  # contact_ids - (optional) is a type of list of number
  contact_ids = var.contact_ids
  # domain_id - (required) is a type of string
  domain_id = var.domain_id
  # geo_location - (optional) is a type of map of string
  geo_location = var.geo_location
  # gtd_region - (optional) is a type of number
  gtd_region = var.gtd_region
  # host - (optional) is a type of string
  host = var.host
  # name - (required) is a type of string
  name = var.name
  # noanswer - (optional) is a type of bool
  noanswer = var.noanswer
  # note - (optional) is a type of string
  note = var.note
  # pools - (optional) is a type of list of number
  pools = var.pools
  # record_failover_disable_flag - (optional) is a type of string
  record_failover_disable_flag = var.record_failover_disable_flag
  # record_failover_failover_type - (optional) is a type of string
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
      # check_id - (optional) is a type of number
      check_id = record_failover_values.value["check_id"]
      # disable_flag - (optional) is a type of string
      disable_flag = record_failover_values.value["disable_flag"]
      # sort_order - (optional) is a type of string
      sort_order = record_failover_values.value["sort_order"]
      # value - (optional) is a type of string
      value = record_failover_values.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "contact_ids" {
  description = "returns a list of number"
  value       = data.constellix_cname_record.this.contact_ids
}

output "geo_location" {
  description = "returns a map of string"
  value       = data.constellix_cname_record.this.geo_location
}

output "gtd_region" {
  description = "returns a number"
  value       = data.constellix_cname_record.this.gtd_region
}

output "host" {
  description = "returns a string"
  value       = data.constellix_cname_record.this.host
}

output "id" {
  description = "returns a string"
  value       = data.constellix_cname_record.this.id
}

output "noanswer" {
  description = "returns a bool"
  value       = data.constellix_cname_record.this.noanswer
}

output "note" {
  description = "returns a string"
  value       = data.constellix_cname_record.this.note
}

output "pools" {
  description = "returns a list of number"
  value       = data.constellix_cname_record.this.pools
}

output "record_failover_disable_flag" {
  description = "returns a string"
  value       = data.constellix_cname_record.this.record_failover_disable_flag
}

output "record_failover_failover_type" {
  description = "returns a string"
  value       = data.constellix_cname_record.this.record_failover_failover_type
}

output "record_option" {
  description = "returns a string"
  value       = data.constellix_cname_record.this.record_option
}

output "ttl" {
  description = "returns a number"
  value       = data.constellix_cname_record.this.ttl
}

output "type" {
  description = "returns a string"
  value       = data.constellix_cname_record.this.type
}

output "this" {
  value = constellix_cname_record.this
}
```

[top](#index)