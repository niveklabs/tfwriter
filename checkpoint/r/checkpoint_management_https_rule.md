# checkpoint_management_https_rule

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
module "checkpoint_management_https_rule" {
  source = []

  # action - (optional) is a type of string
  action = null
  # blade - (optional) is a type of set of string
  blade = []
  # certificate - (optional) is a type of string
  certificate = null
  # comments - (optional) is a type of string
  comments = null
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
  # install_on - (optional) is a type of set of string
  install_on = []
  # layer - (required) is a type of string
  layer = null
  # name - (optional) is a type of string
  name = null
  # position - (required) is a type of map of string
  position = {}
  # service - (optional) is a type of set of string
  service = []
  # service_negate - (optional) is a type of bool
  service_negate = null
  # site_category - (optional) is a type of set of string
  site_category = []
  # site_category_negate - (optional) is a type of bool
  site_category_negate = null
  # source - (optional) is a type of set of string
  # source_negate - (optional) is a type of bool
  source_negate = null
  # track - (optional) is a type of string
  track = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional) - Rule inspect level. \"Bypass\" or \"Inspect\"."
  type        = string
  default     = null
}

variable "blade" {
  description = "(optional) - Blades for HTTPS Inspection. Identified by Name or UID to enable the inspection for. \"Anti Bot\",\"Anti Virus\",\"Application Control\",\"Data Awareness\",\"DLP\",\"IPS\",\"Threat Emulation\",\"Url Filtering\"."
  type        = set(string)
  default     = null
}

variable "certificate" {
  description = "(optional) - Internal Server Certificate identified by Name or UID, otherwise, \"Outbound Certificate\" is a default value."
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "destination" {
  description = "(optional) - Collection of Network objects identified by Name or UID that represents connection destination."
  type        = set(string)
  default     = null
}

variable "destination_negate" {
  description = "(optional) - TRUE if \"negate\" value is set for Destination."
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

variable "install_on" {
  description = "(optional) - Which Gateways identified by the name or UID to install the policy on."
  type        = set(string)
  default     = null
}

variable "layer" {
  description = "(required) - Layer that holds the Object. Identified by the Name or UID."
  type        = string
}

variable "name" {
  description = "(optional) - HTTPS rule name."
  type        = string
  default     = null
}

variable "position" {
  description = "(required) - Position in the rulebase."
  type        = map(string)
}

variable "service" {
  description = "(optional) - Collection of Network objects identified by Name or UID that represents connection service."
  type        = set(string)
  default     = null
}

variable "service_negate" {
  description = "(optional) - TRUE if \"negate\" value is set for Service."
  type        = bool
  default     = null
}

variable "site_category" {
  description = "(optional) - Collection of Site Categories objects identified by the name or UID."
  type        = set(string)
  default     = null
}

variable "site_category_negate" {
  description = "(optional) - TRUE if \"negate\" value is set for Site Category."
  type        = bool
  default     = null
}

variable "source" {
  description = "(optional) - Collection of Network objects identified by Name or UID that represents connection source."
  type        = set(string)
  default     = null
}

variable "source_negate" {
  description = "(optional) - TRUE if \"negate\" value is set for Source."
  type        = bool
  default     = null
}

variable "track" {
  description = "(optional) - \"None\",\"Log\",\"Alert\",\"Mail\",\"SNMP trap\",\"Mail\",\"User Alert\", \"User Alert 2\", \"User Alert 3\"."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_https_rule" "this" {
  action               = var.action
  blade                = var.blade
  certificate          = var.certificate
  comments             = var.comments
  destination          = var.destination
  destination_negate   = var.destination_negate
  enabled              = var.enabled
  ignore_errors        = var.ignore_errors
  ignore_warnings      = var.ignore_warnings
  install_on           = var.install_on
  layer                = var.layer
  name                 = var.name
  position             = var.position
  service              = var.service
  service_negate       = var.service_negate
  site_category        = var.site_category
  site_category_negate = var.site_category_negate
  source               = var.source
  source_negate        = var.source_negate
  track                = var.track
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_https_rule.this.id
}

output "this" {
  value = checkpoint_management_https_rule.this
}
```

[top](#index)