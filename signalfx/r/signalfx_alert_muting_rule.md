# signalfx_alert_muting_rule

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_alert_muting_rule" {
  source = "./modules/signalfx/r/signalfx_alert_muting_rule"

  # description - (required) is a type of string
  description = null
  # detectors - (optional) is a type of list of string
  detectors = []
  # start_time - (required) is a type of number
  start_time = null
  # stop_time - (optional) is a type of number
  stop_time = null

  filter = [{
    negated        = null
    property       = null
    property_value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required) - description of the rule"
  type        = string
}

variable "detectors" {
  description = "(optional) - detectors to which this muting rule applies"
  type        = list(string)
  default     = null
}

variable "start_time" {
  description = "(required) - starting time of an alert muting rule as a Unix timestamp, in seconds"
  type        = number
}

variable "stop_time" {
  description = "(optional) - stop time of an alert muting rule as a Unix timestamp, in seconds"
  type        = number
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      negated        = bool
      property       = string
      property_value = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_alert_muting_rule" "this" {
  description = var.description
  detectors   = var.detectors
  start_time  = var.start_time
  stop_time   = var.stop_time

  dynamic "filter" {
    for_each = var.filter
    content {
      negated        = filter.value["negated"]
      property       = filter.value["property"]
      property_value = filter.value["property_value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "effective_start_time" {
  description = "returns a number"
  value       = signalfx_alert_muting_rule.this.effective_start_time
}

output "id" {
  description = "returns a string"
  value       = signalfx_alert_muting_rule.this.id
}

output "this" {
  value = signalfx_alert_muting_rule.this
}
```

[top](#index)