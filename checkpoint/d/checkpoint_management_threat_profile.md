# checkpoint_management_threat_profile

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/checkpoint/d/checkpoint_management_threat_profile"

  # name - (optional) is a type of string
  name = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Object name. Should be unique in the domain."
  type        = string
  default     = null
}

variable "uid" {
  description = "(optional) - Object unique identifier."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "checkpoint_management_threat_profile" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "activate_protections_by_extended_attributes" {
  description = "returns a list of object"
  value       = data.checkpoint_management_threat_profile.this.activate_protections_by_extended_attributes
}

output "active_protections_performance_impact" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_profile.this.active_protections_performance_impact
}

output "active_protections_severity" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_profile.this.active_protections_severity
}

output "anti_bot" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_profile.this.anti_bot
}

output "anti_virus" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_profile.this.anti_virus
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_profile.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_profile.this.comments
}

output "confidence_level_high" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_profile.this.confidence_level_high
}

output "confidence_level_low" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_profile.this.confidence_level_low
}

output "confidence_level_medium" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_profile.this.confidence_level_medium
}

output "deactivate_protections_by_extended_attributes" {
  description = "returns a list of object"
  value       = data.checkpoint_management_threat_profile.this.deactivate_protections_by_extended_attributes
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_profile.this.id
}

output "indicator_overrides" {
  description = "returns a list of object"
  value       = data.checkpoint_management_threat_profile.this.indicator_overrides
}

output "ips" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_profile.this.ips
}

output "ips_settings" {
  description = "returns a map of string"
  value       = data.checkpoint_management_threat_profile.this.ips_settings
}

output "malicious_mail_policy_settings" {
  description = "returns a map of string"
  value       = data.checkpoint_management_threat_profile.this.malicious_mail_policy_settings
}

output "overrides" {
  description = "returns a list of object"
  value       = data.checkpoint_management_threat_profile.this.overrides
}

output "scan_malicious_links" {
  description = "returns a map of string"
  value       = data.checkpoint_management_threat_profile.this.scan_malicious_links
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_threat_profile.this.tags
}

output "threat_emulation" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_profile.this.threat_emulation
}

output "use_extended_attributes" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_profile.this.use_extended_attributes
}

output "use_indicators" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_profile.this.use_indicators
}

output "this" {
  value = checkpoint_management_threat_profile.this
}
```

[top](#index)