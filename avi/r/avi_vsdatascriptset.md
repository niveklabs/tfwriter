# avi_vsdatascriptset

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_vsdatascriptset" {
  source = "./modules/avi/r/avi_vsdatascriptset"

  # created_by - (optional) is a type of string
  created_by = null
  # description - (optional) is a type of string
  description = null
  # ipgroup_refs - (optional) is a type of list of string
  ipgroup_refs = []
  # name - (required) is a type of string
  name = null
  # pool_group_refs - (optional) is a type of list of string
  pool_group_refs = []
  # pool_refs - (optional) is a type of list of string
  pool_refs = []
  # protocol_parser_refs - (optional) is a type of list of string
  protocol_parser_refs = []
  # string_group_refs - (optional) is a type of list of string
  string_group_refs = []
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  datascript = [{
    evt    = null
    script = null
  }]

  rate_limiters = [{
    burst_sz = null
    count    = null
    name     = null
    period   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipgroup_refs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "pool_group_refs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "pool_refs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "protocol_parser_refs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "string_group_refs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "datascript" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      evt    = string
      script = string
    }
  ))
  default = []
}

variable "rate_limiters" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      burst_sz = number
      count    = number
      name     = string
      period   = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_vsdatascriptset" "this" {
  # created_by - (optional) is a type of string
  created_by = var.created_by
  # description - (optional) is a type of string
  description = var.description
  # ipgroup_refs - (optional) is a type of list of string
  ipgroup_refs = var.ipgroup_refs
  # name - (required) is a type of string
  name = var.name
  # pool_group_refs - (optional) is a type of list of string
  pool_group_refs = var.pool_group_refs
  # pool_refs - (optional) is a type of list of string
  pool_refs = var.pool_refs
  # protocol_parser_refs - (optional) is a type of list of string
  protocol_parser_refs = var.protocol_parser_refs
  # string_group_refs - (optional) is a type of list of string
  string_group_refs = var.string_group_refs
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "datascript" {
    for_each = var.datascript
    content {
      # evt - (required) is a type of string
      evt = datascript.value["evt"]
      # script - (required) is a type of string
      script = datascript.value["script"]
    }
  }

  dynamic "rate_limiters" {
    for_each = var.rate_limiters
    content {
      # burst_sz - (optional) is a type of number
      burst_sz = rate_limiters.value["burst_sz"]
      # count - (optional) is a type of number
      count = rate_limiters.value["count"]
      # name - (optional) is a type of string
      name = rate_limiters.value["name"]
      # period - (optional) is a type of number
      period = rate_limiters.value["period"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_by" {
  description = "returns a string"
  value       = avi_vsdatascriptset.this.created_by
}

output "description" {
  description = "returns a string"
  value       = avi_vsdatascriptset.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_vsdatascriptset.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_vsdatascriptset.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_vsdatascriptset.this.uuid
}

output "this" {
  value = avi_vsdatascriptset.this
}
```

[top](#index)