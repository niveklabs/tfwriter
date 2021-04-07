# oci_monitoring_alarm_history_collection

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_monitoring_alarm_history_collection" {
  source = "./modules/oci/d/oci_monitoring_alarm_history_collection"

  # alarm_historytype - (optional) is a type of string
  alarm_historytype = null
  # alarm_id - (required) is a type of string
  alarm_id = null
  # timestamp_greater_than_or_equal_to - (optional) is a type of string
  timestamp_greater_than_or_equal_to = null
  # timestamp_less_than - (optional) is a type of string
  timestamp_less_than = null
}
```

[top](#index)

### Variables

```terraform
variable "alarm_historytype" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alarm_id" {
  description = "(required)"
  type        = string
}

variable "timestamp_greater_than_or_equal_to" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timestamp_less_than" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "oci_monitoring_alarm_history_collection" "this" {
  alarm_historytype                  = var.alarm_historytype
  alarm_id                           = var.alarm_id
  timestamp_greater_than_or_equal_to = var.timestamp_greater_than_or_equal_to
  timestamp_less_than                = var.timestamp_less_than
}
```

[top](#index)

### Outputs

```terraform
output "entries" {
  description = "returns a list of object"
  value       = data.oci_monitoring_alarm_history_collection.this.entries
}

output "id" {
  description = "returns a string"
  value       = data.oci_monitoring_alarm_history_collection.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = data.oci_monitoring_alarm_history_collection.this.is_enabled
}

output "this" {
  value = oci_monitoring_alarm_history_collection.this
}
```

[top](#index)