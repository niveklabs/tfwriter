# prismacloud_policy

[back](../prismacloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    prismacloud = ">= 1.0.8"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "prismacloud_policy" {
  source = "./modules/prismacloud/r/prismacloud_policy"

  # cloud_type - (optional) is a type of string
  cloud_type = null
  # deleted - (optional) is a type of bool
  deleted = null
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # labels - (optional) is a type of set of string
  labels = []
  # name - (required) is a type of string
  name = null
  # overridden - (optional) is a type of bool
  overridden = null
  # policy_type - (required) is a type of string
  policy_type = null
  # recommendation - (optional) is a type of string
  recommendation = null
  # remediable - (optional) is a type of bool
  remediable = null
  # restrict_alert_dismissal - (optional) is a type of bool
  restrict_alert_dismissal = null
  # severity - (optional) is a type of string
  severity = null
  # system_default - (optional) is a type of bool
  system_default = null

  compliance_metadata = [{
    compliance_id           = null
    custom_assigned         = null
    policy_id               = null
    requirement_description = null
    requirement_id          = null
    requirement_name        = null
    section_description     = null
    section_id              = null
    section_label           = null
    standard_description    = null
    standard_name           = null
  }]

  remediation = [{
    cli_script_json_schema_string = null
    cli_script_template           = null
    description                   = null
    template_type                 = null
  }]

  rule = [{
    api_name         = null
    cloud_account    = null
    cloud_type       = null
    criteria         = null
    name             = null
    parameters       = {}
    resource_id_path = null
    resource_type    = null
    rule_type        = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cloud_type" {
  description = "(optional) - Cloud type (Required for config policies)"
  type        = string
  default     = null
}

variable "deleted" {
  description = "(optional) - Deleted"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - Enabled"
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - Labels"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - Name"
  type        = string
}

variable "overridden" {
  description = "(optional) - Overridden"
  type        = bool
  default     = null
}

variable "policy_type" {
  description = "(required) - Policy type"
  type        = string
}

variable "recommendation" {
  description = "(optional) - Remediation recommendation"
  type        = string
  default     = null
}

variable "remediable" {
  description = "(optional) - Is remediable or not"
  type        = bool
  default     = null
}

variable "restrict_alert_dismissal" {
  description = "(optional) - Restrict alert dismissal"
  type        = bool
  default     = null
}

variable "severity" {
  description = "(optional) - Severity"
  type        = string
  default     = null
}

variable "system_default" {
  description = "(optional) - If policy is a system default policy or not"
  type        = bool
  default     = null
}

variable "compliance_metadata" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      compliance_id           = string
      custom_assigned         = bool
      policy_id               = string
      requirement_description = string
      requirement_id          = string
      requirement_name        = string
      section_description     = string
      section_id              = string
      section_label           = string
      standard_description    = string
      standard_name           = string
    }
  ))
  default = []
}

variable "remediation" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cli_script_json_schema_string = string
      cli_script_template           = string
      description                   = string
      template_type                 = string
    }
  ))
  default = []
}

variable "rule" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      api_name         = string
      cloud_account    = string
      cloud_type       = string
      criteria         = string
      name             = string
      parameters       = map(string)
      resource_id_path = string
      resource_type    = string
      rule_type        = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "prismacloud_policy" "this" {
  cloud_type               = var.cloud_type
  deleted                  = var.deleted
  description              = var.description
  enabled                  = var.enabled
  labels                   = var.labels
  name                     = var.name
  overridden               = var.overridden
  policy_type              = var.policy_type
  recommendation           = var.recommendation
  remediable               = var.remediable
  restrict_alert_dismissal = var.restrict_alert_dismissal
  severity                 = var.severity
  system_default           = var.system_default

  dynamic "compliance_metadata" {
    for_each = var.compliance_metadata
    content {
      compliance_id           = compliance_metadata.value["compliance_id"]
      custom_assigned         = compliance_metadata.value["custom_assigned"]
      policy_id               = compliance_metadata.value["policy_id"]
      requirement_description = compliance_metadata.value["requirement_description"]
      requirement_id          = compliance_metadata.value["requirement_id"]
      requirement_name        = compliance_metadata.value["requirement_name"]
      section_description     = compliance_metadata.value["section_description"]
      section_id              = compliance_metadata.value["section_id"]
      section_label           = compliance_metadata.value["section_label"]
      standard_description    = compliance_metadata.value["standard_description"]
      standard_name           = compliance_metadata.value["standard_name"]
    }
  }

  dynamic "remediation" {
    for_each = var.remediation
    content {
      cli_script_json_schema_string = remediation.value["cli_script_json_schema_string"]
      cli_script_template           = remediation.value["cli_script_template"]
      description                   = remediation.value["description"]
      template_type                 = remediation.value["template_type"]
    }
  }

  dynamic "rule" {
    for_each = var.rule
    content {
      api_name         = rule.value["api_name"]
      cloud_account    = rule.value["cloud_account"]
      cloud_type       = rule.value["cloud_type"]
      criteria         = rule.value["criteria"]
      name             = rule.value["name"]
      parameters       = rule.value["parameters"]
      resource_id_path = rule.value["resource_id_path"]
      resource_type    = rule.value["resource_type"]
      rule_type        = rule.value["rule_type"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_by" {
  description = "returns a string"
  value       = prismacloud_policy.this.created_by
}

output "created_on" {
  description = "returns a number"
  value       = prismacloud_policy.this.created_on
}

output "id" {
  description = "returns a string"
  value       = prismacloud_policy.this.id
}

output "last_modified_by" {
  description = "returns a string"
  value       = prismacloud_policy.this.last_modified_by
}

output "last_modified_on" {
  description = "returns a number"
  value       = prismacloud_policy.this.last_modified_on
}

output "open_alerts_count" {
  description = "returns a number"
  value       = prismacloud_policy.this.open_alerts_count
}

output "owner" {
  description = "returns a string"
  value       = prismacloud_policy.this.owner
}

output "policy_id" {
  description = "returns a string"
  value       = prismacloud_policy.this.policy_id
}

output "policy_mode" {
  description = "returns a string"
  value       = prismacloud_policy.this.policy_mode
}

output "rule_last_modified_on" {
  description = "returns a number"
  value       = prismacloud_policy.this.rule_last_modified_on
}

output "this" {
  value = prismacloud_policy.this
}
```

[top](#index)