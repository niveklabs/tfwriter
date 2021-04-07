# checkpoint_management_threat_profile

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
module "checkpoint_management_threat_profile" {
  source = "./modules/checkpoint/r/checkpoint_management_threat_profile"

  # active_protections_performance_impact - (optional) is a type of string
  active_protections_performance_impact = null
  # active_protections_severity - (optional) is a type of string
  active_protections_severity = null
  # anti_bot - (optional) is a type of bool
  anti_bot = null
  # anti_virus - (optional) is a type of bool
  anti_virus = null
  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # confidence_level_high - (optional) is a type of string
  confidence_level_high = null
  # confidence_level_low - (optional) is a type of string
  confidence_level_low = null
  # confidence_level_medium - (optional) is a type of string
  confidence_level_medium = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # ips - (optional) is a type of bool
  ips = null
  # ips_settings - (optional) is a type of map of string
  ips_settings = {}
  # malicious_mail_policy_settings - (optional) is a type of map of string
  malicious_mail_policy_settings = {}
  # name - (required) is a type of string
  name = null
  # scan_malicious_links - (optional) is a type of map of string
  scan_malicious_links = {}
  # tags - (optional) is a type of set of string
  tags = []
  # threat_emulation - (optional) is a type of bool
  threat_emulation = null
  # use_extended_attributes - (optional) is a type of bool
  use_extended_attributes = null
  # use_indicators - (optional) is a type of bool
  use_indicators = null

  deactivate_protections_by_extended_attributes = [{
    category = null
    name     = null
    uid      = null
    values = [{
      name = null
      uid  = null
    }]
  }]

  indicator_overrides = [{
    action    = null
    indicator = null
  }]

  overrides = [{
    action                   = null
    capture_packets          = null
    default                  = {}
    final                    = {}
    protection               = null
    protection_external_info = []
    protection_uid           = null
    track                    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "active_protections_performance_impact" {
  description = "(optional) - Protections with this performance impact only will be activated in the profile."
  type        = string
  default     = null
}

variable "active_protections_severity" {
  description = "(optional) - Protections with this severity only will be activated in the profile."
  type        = string
  default     = null
}

variable "anti_bot" {
  description = "(optional) - Is Anti-Bot blade activated."
  type        = bool
  default     = null
}

variable "anti_virus" {
  description = "(optional) - Is Anti-Virus blade activated."
  type        = bool
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

variable "confidence_level_high" {
  description = "(optional) - Action for protections with high confidence level."
  type        = string
  default     = null
}

variable "confidence_level_low" {
  description = "(optional) - Action for protections with low confidence level."
  type        = string
  default     = null
}

variable "confidence_level_medium" {
  description = "(optional) - Action for protections with medium confidence level."
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

variable "ips" {
  description = "(optional) - Is IPS blade activated."
  type        = bool
  default     = null
}

variable "ips_settings" {
  description = "(optional) - IPS blade settings."
  type        = map(string)
  default     = null
}

variable "malicious_mail_policy_settings" {
  description = "(optional) - Malicious Mail Policy for MTA Gateways."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Object name. Should be unique in the domain."
  type        = string
}

variable "scan_malicious_links" {
  description = "(optional) - Scans malicious links (URLs) inside email messages."
  type        = map(string)
  default     = null
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "threat_emulation" {
  description = "(optional) - Is Threat Emulation blade activated."
  type        = bool
  default     = null
}

variable "use_extended_attributes" {
  description = "(optional) - Whether to activate/deactivate IPS protections according to the extended attributes."
  type        = bool
  default     = null
}

variable "use_indicators" {
  description = "(optional) - Indicates whether the profile should make use of indicators."
  type        = bool
  default     = null
}

variable "deactivate_protections_by_extended_attributes" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      category = string
      name     = string
      uid      = string
      values = list(object(
        {
          name = string
          uid  = string
        }
      ))
    }
  ))
  default = []
}

variable "indicator_overrides" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action    = string
      indicator = string
    }
  ))
  default = []
}

variable "overrides" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action                   = string
      capture_packets          = bool
      default                  = map(string)
      final                    = map(string)
      protection               = string
      protection_external_info = set(string)
      protection_uid           = string
      track                    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_threat_profile" "this" {
  # active_protections_performance_impact - (optional) is a type of string
  active_protections_performance_impact = var.active_protections_performance_impact
  # active_protections_severity - (optional) is a type of string
  active_protections_severity = var.active_protections_severity
  # anti_bot - (optional) is a type of bool
  anti_bot = var.anti_bot
  # anti_virus - (optional) is a type of bool
  anti_virus = var.anti_virus
  # color - (optional) is a type of string
  color = var.color
  # comments - (optional) is a type of string
  comments = var.comments
  # confidence_level_high - (optional) is a type of string
  confidence_level_high = var.confidence_level_high
  # confidence_level_low - (optional) is a type of string
  confidence_level_low = var.confidence_level_low
  # confidence_level_medium - (optional) is a type of string
  confidence_level_medium = var.confidence_level_medium
  # ignore_errors - (optional) is a type of bool
  ignore_errors = var.ignore_errors
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = var.ignore_warnings
  # ips - (optional) is a type of bool
  ips = var.ips
  # ips_settings - (optional) is a type of map of string
  ips_settings = var.ips_settings
  # malicious_mail_policy_settings - (optional) is a type of map of string
  malicious_mail_policy_settings = var.malicious_mail_policy_settings
  # name - (required) is a type of string
  name = var.name
  # scan_malicious_links - (optional) is a type of map of string
  scan_malicious_links = var.scan_malicious_links
  # tags - (optional) is a type of set of string
  tags = var.tags
  # threat_emulation - (optional) is a type of bool
  threat_emulation = var.threat_emulation
  # use_extended_attributes - (optional) is a type of bool
  use_extended_attributes = var.use_extended_attributes
  # use_indicators - (optional) is a type of bool
  use_indicators = var.use_indicators

  dynamic "deactivate_protections_by_extended_attributes" {
    for_each = var.deactivate_protections_by_extended_attributes
    content {
      # category - (optional) is a type of string
      category = deactivate_protections_by_extended_attributes.value["category"]
      # name - (optional) is a type of string
      name = deactivate_protections_by_extended_attributes.value["name"]
      # uid - (optional) is a type of string
      uid = deactivate_protections_by_extended_attributes.value["uid"]
    }
  }

  dynamic "indicator_overrides" {
    for_each = var.indicator_overrides
    content {
      # action - (optional) is a type of string
      action = indicator_overrides.value["action"]
      # indicator - (optional) is a type of string
      indicator = indicator_overrides.value["indicator"]
    }
  }

  dynamic "overrides" {
    for_each = var.overrides
    content {
      # action - (required) is a type of string
      action = overrides.value["action"]
      # capture_packets - (optional) is a type of bool
      capture_packets = overrides.value["capture_packets"]
      # protection - (required) is a type of string
      protection = overrides.value["protection"]
      # track - (optional) is a type of string
      track = overrides.value["track"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "activate_protections_by_extended_attributes" {
  description = "returns a list of object"
  value       = checkpoint_management_threat_profile.this.activate_protections_by_extended_attributes
}

output "id" {
  description = "returns a string"
  value       = checkpoint_management_threat_profile.this.id
}

output "this" {
  value = checkpoint_management_threat_profile.this
}
```

[top](#index)