# checkpoint_management_access_rule

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_access_rule" {
  source = []

  # action - (optional) is a type of string
  action = null
  # action_settings - (optional) is a type of map of string
  action_settings = {}
  # comments - (optional) is a type of string
  comments = null
  # content - (optional) is a type of set of string
  content = []
  # content_direction - (optional) is a type of string
  content_direction = null
  # content_negate - (optional) is a type of bool
  content_negate = null
  # custom_fields - (optional) is a type of map of string
  custom_fields = {}
  # destination - (optional) is a type of set of string
  destination = []
  # destination_negate - (optional) is a type of bool
  destination_negate = null
  # enabled - (optional) is a type of bool
  enabled = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # inline_layer - (optional) is a type of string
  inline_layer = null
  # install_on - (optional) is a type of set of string
  install_on = []
  # layer - (required) is a type of string
  layer = null
  # name - (required) is a type of string
  name = null
  # position - (required) is a type of map of string
  position = {}
  # service - (optional) is a type of set of string
  service = []
  # service_negate - (optional) is a type of bool
  service_negate = null
  # source - (optional) is a type of set of string
  # source_negate - (optional) is a type of bool
  source_negate = null
  # time - (optional) is a type of set of string
  time = []
  # track - (optional) is a type of map of string
  track = {}
  # vpn - (optional) is a type of string
  vpn = null

  user_check = [{
    confirm = null
    custom_frequency = [{
      every = null
      unit  = null
    }]
    frequency   = null
    interaction = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional) - \"Accept\", \"Drop\", \"Ask\", \"Inform\", \"Reject\", \"User Auth\", \"Client Auth\", \"Apply Layer\"."
  type        = string
  default     = null
}

variable "action_settings" {
  description = "(optional) - Action settings."
  type        = map(string)
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "content" {
  description = "(optional) - List of processed file types that this rule applies on."
  type        = set(string)
  default     = null
}

variable "content_direction" {
  description = "(optional) - On which direction the file types processing is applied."
  type        = string
  default     = null
}

variable "content_negate" {
  description = "(optional) - True if negate is set for data."
  type        = bool
  default     = null
}

variable "custom_fields" {
  description = "(optional) - Custom fields."
  type        = map(string)
  default     = null
}

variable "destination" {
  description = "(optional) - Collection of Network objects identified by the name or UID."
  type        = set(string)
  default     = null
}

variable "destination_negate" {
  description = "(optional) - True if negate is set for destination."
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional) - Enable/Disable the rule."
  type        = bool
  default     = null
}

variable "ignore_errors" {
  description = "(optional) - Apply changes ignoring errors. You won't be able to publish such a changes. If ignore-warnings flag was omitted - warnings will also be ignored."
  type        = bool
  default     = null
}

variable "ignore_warnings" {
  description = "(optional) - Apply changes ignoring warnings."
  type        = bool
  default     = null
}

variable "inline_layer" {
  description = "(optional) - Inline Layer identified by the name or UID. Relevant only if \"Action\" was set to \"Apply Layer\"."
  type        = string
  default     = null
}

variable "install_on" {
  description = "(optional) - Which Gateways identified by the name or UID to install the policy on."
  type        = set(string)
  default     = null
}

variable "layer" {
  description = "(required) - Layer that the rule belongs to identified by the name or UID."
  type        = string
}

variable "name" {
  description = "(required) - Rule name."
  type        = string
}

variable "position" {
  description = "(required) - Position in the rulebase."
  type        = map(string)
}

variable "service" {
  description = "(optional) - Collection of Network objects identified by the name or UID."
  type        = set(string)
  default     = null
}

variable "service_negate" {
  description = "(optional) - True if negate is set for service."
  type        = bool
  default     = null
}

variable "source" {
  description = "(optional) - Collection of Network objects identified by the name or UID."
  type        = set(string)
  default     = null
}

variable "source_negate" {
  description = "(optional) - True if negate is set for source."
  type        = bool
  default     = null
}

variable "time" {
  description = "(optional) - List of time objects. For example: \"Weekend\", \"Off-Work\", \"Every-Day\"."
  type        = set(string)
  default     = null
}

variable "track" {
  description = "(optional) - Track Settings."
  type        = map(string)
  default     = null
}

variable "vpn" {
  description = "(optional) - Communities or Directional."
  type        = string
  default     = null
}

variable "user_check" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      confirm = string
      custom_frequency = list(object(
        {
          every = number
          unit  = string
        }
      ))
      frequency   = string
      interaction = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_access_rule" "this" {
  # action - (optional) is a type of string
  action = var.action
  # action_settings - (optional) is a type of map of string
  action_settings = var.action_settings
  # comments - (optional) is a type of string
  comments = var.comments
  # content - (optional) is a type of set of string
  content = var.content
  # content_direction - (optional) is a type of string
  content_direction = var.content_direction
  # content_negate - (optional) is a type of bool
  content_negate = var.content_negate
  # custom_fields - (optional) is a type of map of string
  custom_fields = var.custom_fields
  # destination - (optional) is a type of set of string
  destination = var.destination
  # destination_negate - (optional) is a type of bool
  destination_negate = var.destination_negate
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # inline_layer - (optional) is a type of string
  inline_layer = var.inline_layer
  # install_on - (optional) is a type of set of string
  install_on = var.install_on
  # layer - (required) is a type of string
  layer = var.layer
  # name - (required) is a type of string
  name = var.name
  # position - (required) is a type of map of string
  position = var.position
  # service - (optional) is a type of set of string
  service = var.service
  # service_negate - (optional) is a type of bool
  service_negate = var.service_negate
  # source - (optional) is a type of set of string
  source = var.source
  # source_negate - (optional) is a type of bool
  source_negate = var.source_negate
  # time - (optional) is a type of set of string
  time = var.time
  # track - (optional) is a type of map of string
  track = var.track
  # vpn - (optional) is a type of string
  vpn = var.vpn

  dynamic "user_check" {
    for_each = var.user_check
    content {
      # confirm - (optional) is a type of string
      confirm = user_check.value["confirm"]
      # frequency - (optional) is a type of string
      frequency = user_check.value["frequency"]
      # interaction - (optional) is a type of string
      interaction = user_check.value["interaction"]

      dynamic "custom_frequency" {
        for_each = user_check.value.custom_frequency
        content {
          # every - (optional) is a type of number
          every = custom_frequency.value["every"]
          # unit - (optional) is a type of string
          unit = custom_frequency.value["unit"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_access_rule.this.id
}

output "this" {
  value = checkpoint_management_access_rule.this
}
```

[top](#index)