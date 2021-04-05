# panos_data_filtering_security_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_data_filtering_security_profile" {
  source = "./modules/panos/r/panos_data_filtering_security_profile"

  # data_capture - (optional) is a type of bool
  data_capture = null
  # description - (optional) is a type of string
  description = null
  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # vsys - (optional) is a type of string
  vsys = null

  rule = [{
    alert_threshold = null
    applications    = []
    block_threshold = null
    data_pattern    = null
    direction       = null
    file_types      = []
    log_severity    = null
    name            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "data_capture" {
  description = "(optional) - Data capture"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Security profile name"
  type        = string
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      alert_threshold = number
      applications    = list(string)
      block_threshold = number
      data_pattern    = string
      direction       = string
      file_types      = list(string)
      log_severity    = string
      name            = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_data_filtering_security_profile" "this" {
  data_capture = var.data_capture
  description  = var.description
  device_group = var.device_group
  name         = var.name
  vsys         = var.vsys

  dynamic "rule" {
    for_each = var.rule
    content {
      alert_threshold = rule.value["alert_threshold"]
      applications    = rule.value["applications"]
      block_threshold = rule.value["block_threshold"]
      data_pattern    = rule.value["data_pattern"]
      direction       = rule.value["direction"]
      file_types      = rule.value["file_types"]
      log_severity    = rule.value["log_severity"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_data_filtering_security_profile.this.id
}

output "this" {
  value = panos_data_filtering_security_profile.this
}
```

[top](#index)