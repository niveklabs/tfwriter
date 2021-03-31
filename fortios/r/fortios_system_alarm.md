# fortios_system_alarm

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_alarm" {
  source = "./modules/fortios/r/fortios_system_alarm"

  # audible - (optional) is a type of string
  audible = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # status - (optional) is a type of string
  status = null

  groups = [{
    admin_auth_failure_threshold = null
    admin_auth_lockout_threshold = null
    decryption_failure_threshold = null
    encryption_failure_threshold = null
    fw_policy_id                 = null
    fw_policy_id_threshold       = null
    fw_policy_violations = [{
      dst_ip    = null
      dst_port  = null
      id        = null
      src_ip    = null
      src_port  = null
      threshold = null
    }]
    id                          = null
    log_full_warning_threshold  = null
    period                      = null
    replay_attempt_threshold    = null
    self_test_failure_threshold = null
    user_auth_failure_threshold = null
    user_auth_lockout_threshold = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "audible" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "groups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      admin_auth_failure_threshold = number
      admin_auth_lockout_threshold = number
      decryption_failure_threshold = number
      encryption_failure_threshold = number
      fw_policy_id                 = number
      fw_policy_id_threshold       = number
      fw_policy_violations = list(object(
        {
          dst_ip    = string
          dst_port  = number
          id        = number
          src_ip    = string
          src_port  = number
          threshold = number
        }
      ))
      id                          = number
      log_full_warning_threshold  = number
      period                      = number
      replay_attempt_threshold    = number
      self_test_failure_threshold = number
      user_auth_failure_threshold = number
      user_auth_lockout_threshold = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_alarm" "this" {
  audible               = var.audible
  dynamic_sort_subtable = var.dynamic_sort_subtable
  status                = var.status

  dynamic "groups" {
    for_each = var.groups
    content {
      admin_auth_failure_threshold = groups.value["admin_auth_failure_threshold"]
      admin_auth_lockout_threshold = groups.value["admin_auth_lockout_threshold"]
      decryption_failure_threshold = groups.value["decryption_failure_threshold"]
      encryption_failure_threshold = groups.value["encryption_failure_threshold"]
      fw_policy_id                 = groups.value["fw_policy_id"]
      fw_policy_id_threshold       = groups.value["fw_policy_id_threshold"]
      id                           = groups.value["id"]
      log_full_warning_threshold   = groups.value["log_full_warning_threshold"]
      period                       = groups.value["period"]
      replay_attempt_threshold     = groups.value["replay_attempt_threshold"]
      self_test_failure_threshold  = groups.value["self_test_failure_threshold"]
      user_auth_failure_threshold  = groups.value["user_auth_failure_threshold"]
      user_auth_lockout_threshold  = groups.value["user_auth_lockout_threshold"]

      dynamic "fw_policy_violations" {
        for_each = groups.value.fw_policy_violations
        content {
          dst_ip    = fw_policy_violations.value["dst_ip"]
          dst_port  = fw_policy_violations.value["dst_port"]
          id        = fw_policy_violations.value["id"]
          src_ip    = fw_policy_violations.value["src_ip"]
          src_port  = fw_policy_violations.value["src_port"]
          threshold = fw_policy_violations.value["threshold"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "audible" {
  description = "returns a string"
  value       = fortios_system_alarm.this.audible
}

output "id" {
  description = "returns a string"
  value       = fortios_system_alarm.this.id
}

output "status" {
  description = "returns a string"
  value       = fortios_system_alarm.this.status
}

output "this" {
  value = fortios_system_alarm.this
}
```

[top](#index)