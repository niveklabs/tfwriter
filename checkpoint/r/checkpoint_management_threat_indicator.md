# checkpoint_management_threat_indicator

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
module "checkpoint_management_threat_indicator" {
  source = "./modules/checkpoint/r/checkpoint_management_threat_indicator"

  # action - (optional) is a type of string
  action = null
  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []

  observables = [{
    confidence       = null
    domain           = null
    ip_address       = null
    ip_address_first = null
    ip_address_last  = null
    mail_cc          = null
    mail_from        = null
    mail_reply_to    = null
    mail_subject     = null
    mail_to          = null
    md5              = null
    name             = null
    product          = null
    severity         = null
    url              = null
  }]

  profile_overrides = [{
    action  = null
    profile = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional) - The indicator's action."
  type        = string
  default     = null
}

variable "color" {
  description = "(optional) - Color of the object. Should be one of existing colors."
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
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

variable "name" {
  description = "(required) - Object name. Should be unique in the domain."
  type        = string
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "observables" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      confidence       = string
      domain           = string
      ip_address       = string
      ip_address_first = string
      ip_address_last  = string
      mail_cc          = string
      mail_from        = string
      mail_reply_to    = string
      mail_subject     = string
      mail_to          = string
      md5              = string
      name             = string
      product          = string
      severity         = string
      url              = string
    }
  ))
  default = []
}

variable "profile_overrides" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action  = string
      profile = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_threat_indicator" "this" {
  # action - (optional) is a type of string
  action = var.action
  # color - (optional) is a type of string
  color = var.color
  # comments - (optional) is a type of string
  comments = var.comments
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of set of string
  tags = var.tags

  dynamic "observables" {
    for_each = var.observables
    content {
      # confidence - (optional) is a type of string
      confidence = observables.value["confidence"]
      # domain - (optional) is a type of string
      domain = observables.value["domain"]
      # ip_address - (optional) is a type of string
      ip_address = observables.value["ip_address"]
      # ip_address_first - (optional) is a type of string
      ip_address_first = observables.value["ip_address_first"]
      # ip_address_last - (optional) is a type of string
      ip_address_last = observables.value["ip_address_last"]
      # mail_cc - (optional) is a type of string
      mail_cc = observables.value["mail_cc"]
      # mail_from - (optional) is a type of string
      mail_from = observables.value["mail_from"]
      # mail_reply_to - (optional) is a type of string
      mail_reply_to = observables.value["mail_reply_to"]
      # mail_subject - (optional) is a type of string
      mail_subject = observables.value["mail_subject"]
      # mail_to - (optional) is a type of string
      mail_to = observables.value["mail_to"]
      # md5 - (optional) is a type of string
      md5 = observables.value["md5"]
      # name - (required) is a type of string
      name = observables.value["name"]
      # product - (optional) is a type of string
      product = observables.value["product"]
      # severity - (optional) is a type of string
      severity = observables.value["severity"]
      # url - (optional) is a type of string
      url = observables.value["url"]
    }
  }

  dynamic "profile_overrides" {
    for_each = var.profile_overrides
    content {
      # action - (optional) is a type of string
      action = profile_overrides.value["action"]
      # profile - (optional) is a type of string
      profile = profile_overrides.value["profile"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_threat_indicator.this.id
}

output "this" {
  value = checkpoint_management_threat_indicator.this
}
```

[top](#index)