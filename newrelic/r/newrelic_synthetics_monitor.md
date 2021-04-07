# newrelic_synthetics_monitor

[back](../newrelic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    newrelic = ">= 2.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "newrelic_synthetics_monitor" {
  source = "./modules/newrelic/r/newrelic_synthetics_monitor"

  # bypass_head_request - (optional) is a type of bool
  bypass_head_request = null
  # frequency - (required) is a type of number
  frequency = null
  # locations - (required) is a type of set of string
  locations = []
  # name - (required) is a type of string
  name = null
  # sla_threshold - (optional) is a type of number
  sla_threshold = null
  # status - (required) is a type of string
  status = null
  # treat_redirect_as_failure - (optional) is a type of bool
  treat_redirect_as_failure = null
  # type - (required) is a type of string
  type = null
  # uri - (optional) is a type of string
  uri = null
  # validation_string - (optional) is a type of string
  validation_string = null
  # verify_ssl - (optional) is a type of bool
  verify_ssl = null
}
```

[top](#index)

### Variables

```terraform
variable "bypass_head_request" {
  description = "(optional) - Bypass HEAD request."
  type        = bool
  default     = null
}

variable "frequency" {
  description = "(required) - The interval (in minutes) at which this monitor should run. Valid values are 1, 5, 10, 15, 30, 60, 360, 720, or 1440."
  type        = number
}

variable "locations" {
  description = "(required) - The locations in which this monitor should be run."
  type        = set(string)
}

variable "name" {
  description = "(required) - The title of this monitor."
  type        = string
}

variable "sla_threshold" {
  description = "(optional) - The base threshold for the SLA report."
  type        = number
  default     = null
}

variable "status" {
  description = "(required) - The monitor status (i.e. ENABLED, MUTED, DISABLED)."
  type        = string
}

variable "treat_redirect_as_failure" {
  description = "(optional) - Fail the monitor check if redirected."
  type        = bool
  default     = null
}

variable "type" {
  description = "(required) - The monitor type. Valid values are SIMPLE, BROWSER, SCRIPT_BROWSER, and SCRIPT_API."
  type        = string
}

variable "uri" {
  description = "(optional) - The URI for the monitor to hit."
  type        = string
  default     = null
}

variable "validation_string" {
  description = "(optional) - The string to validate against in the response."
  type        = string
  default     = null
}

variable "verify_ssl" {
  description = "(optional) - Verify SSL."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "newrelic_synthetics_monitor" "this" {
  # bypass_head_request - (optional) is a type of bool
  bypass_head_request = var.bypass_head_request
  # frequency - (required) is a type of number
  frequency = var.frequency
  # locations - (required) is a type of set of string
  locations = var.locations
  # name - (required) is a type of string
  name = var.name
  # sla_threshold - (optional) is a type of number
  sla_threshold = var.sla_threshold
  # status - (required) is a type of string
  status = var.status
  # treat_redirect_as_failure - (optional) is a type of bool
  treat_redirect_as_failure = var.treat_redirect_as_failure
  # type - (required) is a type of string
  type = var.type
  # uri - (optional) is a type of string
  uri = var.uri
  # validation_string - (optional) is a type of string
  validation_string = var.validation_string
  # verify_ssl - (optional) is a type of bool
  verify_ssl = var.verify_ssl
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = newrelic_synthetics_monitor.this.id
}

output "this" {
  value = newrelic_synthetics_monitor.this
}
```

[top](#index)