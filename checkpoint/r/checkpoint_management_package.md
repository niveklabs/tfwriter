# checkpoint_management_package

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
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_package" {
  source = "./modules/checkpoint/r/checkpoint_management_package"

  # access - (optional) is a type of bool
  access = null
  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # desktop_security - (optional) is a type of bool
  desktop_security = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # installation_targets - (optional) is a type of set of string
  installation_targets = []
  # name - (required) is a type of string
  name = null
  # qos - (optional) is a type of bool
  qos = null
  # qos_policy_type - (optional) is a type of string
  qos_policy_type = null
  # tags - (optional) is a type of set of string
  tags = []
  # threat_prevention - (optional) is a type of bool
  threat_prevention = null
  # vpn_traditional_mode - (optional) is a type of bool
  vpn_traditional_mode = null
}
```

[top](#index)

### Variables

```terraform
variable "access" {
  description = "(optional) - True - enables, False - disables access & NAT policies, empty - nothing is changed."
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

variable "desktop_security" {
  description = "(optional) - True - enables, False - disables Desktop security policy, empty - nothing is changed."
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

variable "installation_targets" {
  description = "(optional) - Which Gateways identified by the name or UID to install the policy on."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - Object name. Should be unique in the domain."
  type        = string
}

variable "qos" {
  description = "(optional) - True - enables, False - disables QoS policy, empty - nothing is changed."
  type        = bool
  default     = null
}

variable "qos_policy_type" {
  description = "(optional) - QoS policy type."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "threat_prevention" {
  description = "(optional) - True - enables, False - disables Threat policy, empty - nothing is changed."
  type        = bool
  default     = null
}

variable "vpn_traditional_mode" {
  description = "(optional) - True - enables, False - disables VPN traditional mode, empty - nothing is changed."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_package" "this" {
  access               = var.access
  color                = var.color
  comments             = var.comments
  desktop_security     = var.desktop_security
  ignore_errors        = var.ignore_errors
  ignore_warnings      = var.ignore_warnings
  installation_targets = var.installation_targets
  name                 = var.name
  qos                  = var.qos
  qos_policy_type      = var.qos_policy_type
  tags                 = var.tags
  threat_prevention    = var.threat_prevention
  vpn_traditional_mode = var.vpn_traditional_mode
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_package.this.id
}

output "this" {
  value = checkpoint_management_package.this
}
```

[top](#index)