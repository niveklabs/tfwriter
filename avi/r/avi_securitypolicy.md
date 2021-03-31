# avi_securitypolicy

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_securitypolicy" {
  source = "./modules/avi/r/avi_securitypolicy"

  # description - (optional) is a type of string
  description = null
  # dns_policy_index - (optional) is a type of number
  dns_policy_index = null
  # name - (required) is a type of string
  name = null
  # network_security_policy_index - (optional) is a type of number
  network_security_policy_index = null
  # oper_mode - (optional) is a type of string
  oper_mode = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  dns_attacks = [{
    attacks = [{
      attack_vector      = null
      enabled            = null
      max_mitigation_age = null
      mitigation_action = [{
        deny = null
      }]
      threshold = null
    }]
    oper_mode = null
  }]

  tcp_attacks = [{

  }]

  udp_attacks = [{

  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_policy_index" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_security_policy_index" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "oper_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_attacks" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      attacks = list(object(
        {
          attack_vector      = string
          enabled            = bool
          max_mitigation_age = number
          mitigation_action = set(object(
            {
              deny = bool
            }
          ))
          threshold = number
        }
      ))
      oper_mode = string
    }
  ))
  default = []
}

variable "tcp_attacks" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {

    }
  ))
  default = []
}

variable "udp_attacks" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {

    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_securitypolicy" "this" {
  description                   = var.description
  dns_policy_index              = var.dns_policy_index
  name                          = var.name
  network_security_policy_index = var.network_security_policy_index
  oper_mode                     = var.oper_mode
  tenant_ref                    = var.tenant_ref
  uuid                          = var.uuid

  dynamic "dns_attacks" {
    for_each = var.dns_attacks
    content {
      oper_mode = dns_attacks.value["oper_mode"]

      dynamic "attacks" {
        for_each = dns_attacks.value.attacks
        content {
          attack_vector      = attacks.value["attack_vector"]
          enabled            = attacks.value["enabled"]
          max_mitigation_age = attacks.value["max_mitigation_age"]
          threshold          = attacks.value["threshold"]

          dynamic "mitigation_action" {
            for_each = attacks.value.mitigation_action
            content {
              deny = mitigation_action.value["deny"]
            }
          }

        }
      }

    }
  }

  dynamic "tcp_attacks" {
    for_each = var.tcp_attacks
    content {
    }
  }

  dynamic "udp_attacks" {
    for_each = var.udp_attacks
    content {
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_securitypolicy.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_securitypolicy.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_securitypolicy.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_securitypolicy.this.uuid
}

output "this" {
  value = avi_securitypolicy.this
}
```

[top](#index)