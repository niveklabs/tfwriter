# constellix_caa_record

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
module "constellix_caa_record" {
  source = "./modules/constellix/d/constellix_caa_record"

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
  # source_type - (required) is a type of string
  source_type = null
  # ttl - (optional) is a type of number
  ttl = null
  # type - (optional) is a type of string
  type = null

  roundrobin = [{
    caa_provider_id = null
    data            = null
    disable_flag    = null
    flag            = null
    tag             = null
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
      caa_provider_id = number
      data            = string
      disable_flag    = string
      flag            = string
      tag             = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "constellix_caa_record" "this" {
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
      caa_provider_id = roundrobin.value["caa_provider_id"]
      data            = roundrobin.value["data"]
      disable_flag    = roundrobin.value["disable_flag"]
      flag            = roundrobin.value["flag"]
      tag             = roundrobin.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "gtd_region" {
  description = "returns a number"
  value       = data.constellix_caa_record.this.gtd_region
}

output "id" {
  description = "returns a string"
  value       = data.constellix_caa_record.this.id
}

output "noanswer" {
  description = "returns a bool"
  value       = data.constellix_caa_record.this.noanswer
}

output "note" {
  description = "returns a string"
  value       = data.constellix_caa_record.this.note
}

output "ttl" {
  description = "returns a number"
  value       = data.constellix_caa_record.this.ttl
}

output "type" {
  description = "returns a string"
  value       = data.constellix_caa_record.this.type
}

output "this" {
  value = constellix_caa_record.this
}
```

[top](#index)