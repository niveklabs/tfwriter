# equinix_ecx_l2_serviceprofile

[back](../equinix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    equinix = ">= 1.1.0-beta"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "equinix_ecx_l2_serviceprofile" {
  source = "./modules/equinix/r/equinix_ecx_l2_serviceprofile"

  # api_integration - (optional) is a type of bool
  api_integration = null
  # authkey_label - (optional) is a type of string
  authkey_label = null
  # bandwidth_alert_threshold - (optional) is a type of number
  bandwidth_alert_threshold = null
  # bandwidth_threshold_notifications - (required) is a type of set of string
  bandwidth_threshold_notifications = []
  # connection_name_label - (optional) is a type of string
  connection_name_label = null
  # ctag_label - (optional) is a type of string
  ctag_label = null
  # description - (optional) is a type of string
  description = null
  # equinix_managed_port_vlan - (optional) is a type of bool
  equinix_managed_port_vlan = null
  # integration_id - (optional) is a type of string
  integration_id = null
  # name - (required) is a type of string
  name = null
  # oversubscription - (optional) is a type of string
  oversubscription = null
  # oversubscription_allowed - (optional) is a type of bool
  oversubscription_allowed = null
  # private - (optional) is a type of bool
  private = null
  # private_user_emails - (optional) is a type of set of string
  private_user_emails = []
  # profile_statuschange_notifications - (required) is a type of set of string
  profile_statuschange_notifications = []
  # redundancy_required - (optional) is a type of bool
  redundancy_required = null
  # secondary_vlan_from_primary - (optional) is a type of bool
  secondary_vlan_from_primary = null
  # servicekey_autogenerated - (optional) is a type of bool
  servicekey_autogenerated = null
  # speed_customization_allowed - (optional) is a type of bool
  speed_customization_allowed = null
  # speed_from_api - (optional) is a type of bool
  speed_from_api = null
  # tag_type - (optional) is a type of string
  tag_type = null
  # vc_statuschange_notifications - (required) is a type of set of string
  vc_statuschange_notifications = []

  features = [{
    allow_remote_connections = null
    test_profile             = null
  }]

  port = [{
    metro_code = null
    uuid       = null
  }]

  speed_band = [{
    speed      = null
    speed_unit = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "api_integration" {
  description = "(optional) - Specifies the API integration ID that was provided to the customer during onboarding"
  type        = bool
  default     = null
}

variable "authkey_label" {
  description = "(optional) - Name of the authentication key label to be used by the Authentication Key service"
  type        = string
  default     = null
}

variable "bandwidth_alert_threshold" {
  description = "(optional) - Specifies the port bandwidth threshold percentage. If the bandwidth limit is met or exceeded, an alert is sent to the seller"
  type        = number
  default     = null
}

variable "bandwidth_threshold_notifications" {
  description = "(required) - A list of email addresses that will receive notifications about bandwidth thresholds"
  type        = set(string)
}

variable "connection_name_label" {
  description = "(optional) - Custom name used for calling a connections i.e. circuit. Defaults to Connection"
  type        = string
  default     = null
}

variable "ctag_label" {
  description = "(optional) - C-Tag/Inner-Tag label name for the connections"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description of the service profile"
  type        = string
  default     = null
}

variable "equinix_managed_port_vlan" {
  description = "(optional) - Boolean value that indicates whether the port and VLAN details are managed by Equinix"
  type        = bool
  default     = null
}

variable "integration_id" {
  description = "(optional) - Specifies the API integration ID that was provided to the customer during onboarding"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the service profile. An alpha-numeric 50 characters string which can include only hyphens and underscores"
  type        = string
}

variable "oversubscription" {
  description = "(optional) - Oversubscription limit that will cause alerting. Default is 1x"
  type        = string
  default     = null
}

variable "oversubscription_allowed" {
  description = "(optional) - Boolean value that determines if, regardless of the utilization, Equinix Fabric will continue to add connections to your links until we reach the oversubscription limit"
  type        = bool
  default     = null
}

variable "private" {
  description = "(optional) - Boolean value that indicates whether or not this is a private profile."
  type        = bool
  default     = null
}

variable "private_user_emails" {
  description = "(optional) - A list of email addresses associated to users that will be allowed to access this service profile. Applicable for private profiles"
  type        = set(string)
  default     = null
}

variable "profile_statuschange_notifications" {
  description = "(required) - A list of email addresses that will receive notifications about profile status changes"
  type        = set(string)
}

variable "redundancy_required" {
  description = "(optional) - Boolean value that determines if yourconnections will require redundancy"
  type        = bool
  default     = null
}

variable "secondary_vlan_from_primary" {
  description = "(optional) - Indicates whether the VLAN ID of the secondary connection is the same as the primary connection"
  type        = bool
  default     = null
}

variable "servicekey_autogenerated" {
  description = "(optional) - Boolean value that indicates whether multiple connections can be created with the same authorization key"
  type        = bool
  default     = null
}

variable "speed_customization_allowed" {
  description = "(optional) - Boolean value that determines if customer is allowed to enter a custom connection speed"
  type        = bool
  default     = null
}

variable "speed_from_api" {
  description = "(optional) - Boolean valuta that determines if connection speed will be derived from an API call"
  type        = bool
  default     = null
}

variable "tag_type" {
  description = "(optional) - Specifies additional tagging information required by the seller profile for Dot1Q to QinQ translation"
  type        = string
  default     = null
}

variable "vc_statuschange_notifications" {
  description = "(required) - A list of email addresses that will receive notifications about connections approvals and rejections"
  type        = set(string)
}

variable "features" {
  description = "nested block: NestingSet, min items: 1, max items: 1"
  type = set(object(
    {
      allow_remote_connections = bool
      test_profile             = bool
    }
  ))
}

variable "port" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      metro_code = string
      uuid       = string
    }
  ))
}

variable "speed_band" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      speed      = number
      speed_unit = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "equinix_ecx_l2_serviceprofile" "this" {
  # api_integration - (optional) is a type of bool
  api_integration = var.api_integration
  # authkey_label - (optional) is a type of string
  authkey_label = var.authkey_label
  # bandwidth_alert_threshold - (optional) is a type of number
  bandwidth_alert_threshold = var.bandwidth_alert_threshold
  # bandwidth_threshold_notifications - (required) is a type of set of string
  bandwidth_threshold_notifications = var.bandwidth_threshold_notifications
  # connection_name_label - (optional) is a type of string
  connection_name_label = var.connection_name_label
  # ctag_label - (optional) is a type of string
  ctag_label = var.ctag_label
  # description - (optional) is a type of string
  description = var.description
  # equinix_managed_port_vlan - (optional) is a type of bool
  equinix_managed_port_vlan = var.equinix_managed_port_vlan
  # integration_id - (optional) is a type of string
  integration_id = var.integration_id
  # name - (required) is a type of string
  name = var.name
  # oversubscription - (optional) is a type of string
  oversubscription = var.oversubscription
  # oversubscription_allowed - (optional) is a type of bool
  oversubscription_allowed = var.oversubscription_allowed
  # private - (optional) is a type of bool
  private = var.private
  # private_user_emails - (optional) is a type of set of string
  private_user_emails = var.private_user_emails
  # profile_statuschange_notifications - (required) is a type of set of string
  profile_statuschange_notifications = var.profile_statuschange_notifications
  # redundancy_required - (optional) is a type of bool
  redundancy_required = var.redundancy_required
  # secondary_vlan_from_primary - (optional) is a type of bool
  secondary_vlan_from_primary = var.secondary_vlan_from_primary
  # servicekey_autogenerated - (optional) is a type of bool
  servicekey_autogenerated = var.servicekey_autogenerated
  # speed_customization_allowed - (optional) is a type of bool
  speed_customization_allowed = var.speed_customization_allowed
  # speed_from_api - (optional) is a type of bool
  speed_from_api = var.speed_from_api
  # tag_type - (optional) is a type of string
  tag_type = var.tag_type
  # vc_statuschange_notifications - (required) is a type of set of string
  vc_statuschange_notifications = var.vc_statuschange_notifications

  dynamic "features" {
    for_each = var.features
    content {
      # allow_remote_connections - (required) is a type of bool
      allow_remote_connections = features.value["allow_remote_connections"]
      # test_profile - (required) is a type of bool
      test_profile = features.value["test_profile"]
    }
  }

  dynamic "port" {
    for_each = var.port
    content {
      # metro_code - (required) is a type of string
      metro_code = port.value["metro_code"]
      # uuid - (required) is a type of string
      uuid = port.value["uuid"]
    }
  }

  dynamic "speed_band" {
    for_each = var.speed_band
    content {
      # speed - (required) is a type of number
      speed = speed_band.value["speed"]
      # speed_unit - (required) is a type of string
      speed_unit = speed_band.value["speed_unit"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = equinix_ecx_l2_serviceprofile.this.id
}

output "state" {
  description = "returns a string"
  value       = equinix_ecx_l2_serviceprofile.this.state
}

output "uuid" {
  description = "returns a string"
  value       = equinix_ecx_l2_serviceprofile.this.uuid
}

output "this" {
  value = equinix_ecx_l2_serviceprofile.this
}
```

[top](#index)