# ns1_monitoringjob

[back](../ns1.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ns1 = ">= 1.9.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ns1_monitoringjob" {
  source = "./modules/ns1/r/ns1_monitoringjob"

  # active - (optional) is a type of bool
  active = null
  # config - (required) is a type of map of string
  config = {}
  # frequency - (required) is a type of number
  frequency = null
  # job_type - (required) is a type of string
  job_type = null
  # name - (required) is a type of string
  name = null
  # notes - (optional) is a type of string
  notes = null
  # notify_delay - (optional) is a type of number
  notify_delay = null
  # notify_failback - (optional) is a type of bool
  notify_failback = null
  # notify_list - (optional) is a type of string
  notify_list = null
  # notify_regional - (optional) is a type of bool
  notify_regional = null
  # notify_repeat - (optional) is a type of number
  notify_repeat = null
  # policy - (optional) is a type of string
  policy = null
  # rapid_recheck - (optional) is a type of bool
  rapid_recheck = null
  # regions - (required) is a type of list of string
  regions = []

  rules = [{
    comparison = null
    key        = null
    value      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "config" {
  description = "(required)"
  type        = map(string)
}

variable "frequency" {
  description = "(required)"
  type        = number
}

variable "job_type" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notify_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "notify_failback" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "notify_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notify_regional" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "notify_repeat" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rapid_recheck" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "regions" {
  description = "(required)"
  type        = list(string)
}

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      comparison = string
      key        = string
      value      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ns1_monitoringjob" "this" {
  # active - (optional) is a type of bool
  active = var.active
  # config - (required) is a type of map of string
  config = var.config
  # frequency - (required) is a type of number
  frequency = var.frequency
  # job_type - (required) is a type of string
  job_type = var.job_type
  # name - (required) is a type of string
  name = var.name
  # notes - (optional) is a type of string
  notes = var.notes
  # notify_delay - (optional) is a type of number
  notify_delay = var.notify_delay
  # notify_failback - (optional) is a type of bool
  notify_failback = var.notify_failback
  # notify_list - (optional) is a type of string
  notify_list = var.notify_list
  # notify_regional - (optional) is a type of bool
  notify_regional = var.notify_regional
  # notify_repeat - (optional) is a type of number
  notify_repeat = var.notify_repeat
  # policy - (optional) is a type of string
  policy = var.policy
  # rapid_recheck - (optional) is a type of bool
  rapid_recheck = var.rapid_recheck
  # regions - (required) is a type of list of string
  regions = var.regions

  dynamic "rules" {
    for_each = var.rules
    content {
      # comparison - (required) is a type of string
      comparison = rules.value["comparison"]
      # key - (required) is a type of string
      key = rules.value["key"]
      # value - (required) is a type of string
      value = rules.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ns1_monitoringjob.this.id
}

output "this" {
  value = ns1_monitoringjob.this
}
```

[top](#index)