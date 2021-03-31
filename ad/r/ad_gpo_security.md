# ad_gpo_security

[back](../ad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ad = ">= 0.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ad_gpo_security" {
  source = "./modules/ad/r/ad_gpo_security"

  # gpo_container - (required) is a type of string
  gpo_container = null

  account_lockout = [{
    force_logoff_when_hour_expire = null
    lockout_bad_count             = null
    lockout_duration              = null
    reset_lockout_count           = null
  }]

  application_log = [{
    audit_log_retention_period = null
    maximum_log_size           = null
    restrict_guest_access      = null
    retention_days             = null
  }]

  audit_log = [{
    audit_log_retention_period = null
    maximum_log_size           = null
    restrict_guest_access      = null
    retention_days             = null
  }]

  event_audit = [{
    audit_account_logon    = null
    audit_account_manage   = null
    audit_ds_access        = null
    audit_logon_events     = null
    audit_object_access    = null
    audit_policy_change    = null
    audit_privilege_use    = null
    audit_process_tracking = null
    audit_system_events    = null
  }]

  filesystem = [{
    acl              = null
    path             = null
    propagation_mode = null
  }]

  kerberos_policy = [{
    max_clock_skew         = null
    max_renew_age          = null
    max_service_age        = null
    max_ticket_age         = null
    ticket_validate_client = null
  }]

  password_policies = [{
    clear_text_password     = null
    maximum_password_age    = null
    minimum_password_age    = null
    minimum_password_length = null
    password_complexity     = null
    password_history_size   = null
  }]

  registry_keys = [{
    acl              = null
    key_name         = null
    propagation_mode = null
  }]

  registry_values = [{
    key_name   = null
    value      = null
    value_type = null
  }]

  restricted_groups = [{
    group_memberof = null
    group_members  = null
    group_name     = null
  }]

  system_log = [{
    audit_log_retention_period = null
    maximum_log_size           = null
    restrict_guest_access      = null
    retention_days             = null
  }]

  system_services = [{
    acl          = null
    service_name = null
    startup_mode = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "gpo_container" {
  description = "(required) - The GUID of the container the security settings belong to."
  type        = string
}

variable "account_lockout" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      force_logoff_when_hour_expire = string
      lockout_bad_count             = string
      lockout_duration              = string
      reset_lockout_count           = string
    }
  ))
  default = []
}

variable "application_log" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      audit_log_retention_period = string
      maximum_log_size           = string
      restrict_guest_access      = string
      retention_days             = string
    }
  ))
  default = []
}

variable "audit_log" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      audit_log_retention_period = string
      maximum_log_size           = string
      restrict_guest_access      = string
      retention_days             = string
    }
  ))
  default = []
}

variable "event_audit" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      audit_account_logon    = string
      audit_account_manage   = string
      audit_ds_access        = string
      audit_logon_events     = string
      audit_object_access    = string
      audit_policy_change    = string
      audit_privilege_use    = string
      audit_process_tracking = string
      audit_system_events    = string
    }
  ))
  default = []
}

variable "filesystem" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      acl              = string
      path             = string
      propagation_mode = string
    }
  ))
  default = []
}

variable "kerberos_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_clock_skew         = string
      max_renew_age          = string
      max_service_age        = string
      max_ticket_age         = string
      ticket_validate_client = string
    }
  ))
  default = []
}

variable "password_policies" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      clear_text_password     = string
      maximum_password_age    = string
      minimum_password_age    = string
      minimum_password_length = string
      password_complexity     = string
      password_history_size   = string
    }
  ))
  default = []
}

variable "registry_keys" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      acl              = string
      key_name         = string
      propagation_mode = string
    }
  ))
  default = []
}

variable "registry_values" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key_name   = string
      value      = string
      value_type = string
    }
  ))
  default = []
}

variable "restricted_groups" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      group_memberof = string
      group_members  = string
      group_name     = string
    }
  ))
  default = []
}

variable "system_log" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      audit_log_retention_period = string
      maximum_log_size           = string
      restrict_guest_access      = string
      retention_days             = string
    }
  ))
  default = []
}

variable "system_services" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      acl          = string
      service_name = string
      startup_mode = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ad_gpo_security" "this" {
  gpo_container = var.gpo_container

  dynamic "account_lockout" {
    for_each = var.account_lockout
    content {
      force_logoff_when_hour_expire = account_lockout.value["force_logoff_when_hour_expire"]
      lockout_bad_count             = account_lockout.value["lockout_bad_count"]
      lockout_duration              = account_lockout.value["lockout_duration"]
      reset_lockout_count           = account_lockout.value["reset_lockout_count"]
    }
  }

  dynamic "application_log" {
    for_each = var.application_log
    content {
      audit_log_retention_period = application_log.value["audit_log_retention_period"]
      maximum_log_size           = application_log.value["maximum_log_size"]
      restrict_guest_access      = application_log.value["restrict_guest_access"]
      retention_days             = application_log.value["retention_days"]
    }
  }

  dynamic "audit_log" {
    for_each = var.audit_log
    content {
      audit_log_retention_period = audit_log.value["audit_log_retention_period"]
      maximum_log_size           = audit_log.value["maximum_log_size"]
      restrict_guest_access      = audit_log.value["restrict_guest_access"]
      retention_days             = audit_log.value["retention_days"]
    }
  }

  dynamic "event_audit" {
    for_each = var.event_audit
    content {
      audit_account_logon    = event_audit.value["audit_account_logon"]
      audit_account_manage   = event_audit.value["audit_account_manage"]
      audit_ds_access        = event_audit.value["audit_ds_access"]
      audit_logon_events     = event_audit.value["audit_logon_events"]
      audit_object_access    = event_audit.value["audit_object_access"]
      audit_policy_change    = event_audit.value["audit_policy_change"]
      audit_privilege_use    = event_audit.value["audit_privilege_use"]
      audit_process_tracking = event_audit.value["audit_process_tracking"]
      audit_system_events    = event_audit.value["audit_system_events"]
    }
  }

  dynamic "filesystem" {
    for_each = var.filesystem
    content {
      acl              = filesystem.value["acl"]
      path             = filesystem.value["path"]
      propagation_mode = filesystem.value["propagation_mode"]
    }
  }

  dynamic "kerberos_policy" {
    for_each = var.kerberos_policy
    content {
      max_clock_skew         = kerberos_policy.value["max_clock_skew"]
      max_renew_age          = kerberos_policy.value["max_renew_age"]
      max_service_age        = kerberos_policy.value["max_service_age"]
      max_ticket_age         = kerberos_policy.value["max_ticket_age"]
      ticket_validate_client = kerberos_policy.value["ticket_validate_client"]
    }
  }

  dynamic "password_policies" {
    for_each = var.password_policies
    content {
      clear_text_password     = password_policies.value["clear_text_password"]
      maximum_password_age    = password_policies.value["maximum_password_age"]
      minimum_password_age    = password_policies.value["minimum_password_age"]
      minimum_password_length = password_policies.value["minimum_password_length"]
      password_complexity     = password_policies.value["password_complexity"]
      password_history_size   = password_policies.value["password_history_size"]
    }
  }

  dynamic "registry_keys" {
    for_each = var.registry_keys
    content {
      acl              = registry_keys.value["acl"]
      key_name         = registry_keys.value["key_name"]
      propagation_mode = registry_keys.value["propagation_mode"]
    }
  }

  dynamic "registry_values" {
    for_each = var.registry_values
    content {
      key_name   = registry_values.value["key_name"]
      value      = registry_values.value["value"]
      value_type = registry_values.value["value_type"]
    }
  }

  dynamic "restricted_groups" {
    for_each = var.restricted_groups
    content {
      group_memberof = restricted_groups.value["group_memberof"]
      group_members  = restricted_groups.value["group_members"]
      group_name     = restricted_groups.value["group_name"]
    }
  }

  dynamic "system_log" {
    for_each = var.system_log
    content {
      audit_log_retention_period = system_log.value["audit_log_retention_period"]
      maximum_log_size           = system_log.value["maximum_log_size"]
      restrict_guest_access      = system_log.value["restrict_guest_access"]
      retention_days             = system_log.value["retention_days"]
    }
  }

  dynamic "system_services" {
    for_each = var.system_services
    content {
      acl          = system_services.value["acl"]
      service_name = system_services.value["service_name"]
      startup_mode = system_services.value["startup_mode"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ad_gpo_security.this.id
}

output "this" {
  value = ad_gpo_security.this
}
```

[top](#index)