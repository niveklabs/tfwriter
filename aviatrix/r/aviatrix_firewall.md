# aviatrix_firewall

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_firewall" {
  source = "./modules/aviatrix/r/aviatrix_firewall"

  # base_log_enabled - (optional) is a type of bool
  base_log_enabled = null
  # base_policy - (optional) is a type of string
  base_policy = null
  # gw_name - (required) is a type of string
  gw_name = null
  # manage_firewall_policies - (optional) is a type of bool
  manage_firewall_policies = null

  policy = [{
    action      = null
    description = null
    dst_ip      = null
    log_enabled = null
    port        = null
    protocol    = null
    src_ip      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "base_log_enabled" {
  description = "(optional) - Indicates whether enable logging or not. Valid values: true or false."
  type        = bool
  default     = null
}

variable "base_policy" {
  description = "(optional) - New base policy."
  type        = string
  default     = null
}

variable "gw_name" {
  description = "(required) - The name of gateway."
  type        = string
}

variable "manage_firewall_policies" {
  description = "(optional) - Enable to manage firewall policies via in-line rules. If false, policies must be managed using `aviatrix_firewall_policy` resources."
  type        = bool
  default     = null
}

variable "policy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action      = string
      description = string
      dst_ip      = string
      log_enabled = bool
      port        = string
      protocol    = string
      src_ip      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_firewall" "this" {
  base_log_enabled         = var.base_log_enabled
  base_policy              = var.base_policy
  gw_name                  = var.gw_name
  manage_firewall_policies = var.manage_firewall_policies

  dynamic "policy" {
    for_each = var.policy
    content {
      action      = policy.value["action"]
      description = policy.value["description"]
      dst_ip      = policy.value["dst_ip"]
      log_enabled = policy.value["log_enabled"]
      port        = policy.value["port"]
      protocol    = policy.value["protocol"]
      src_ip      = policy.value["src_ip"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_firewall.this.id
}

output "this" {
  value = aviatrix_firewall.this
}
```

[top](#index)