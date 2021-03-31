# fortios_firewall_security_policyseq

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
module "fortios_firewall_security_policyseq" {
  source = "./modules/fortios/r/fortios_firewall_security_policyseq"

  # alter_position - (required) is a type of string
  alter_position = null
  # comment - (optional) is a type of string
  comment = null
  # enable_state_checking - (optional) is a type of bool
  enable_state_checking = null
  # policy_dst_id - (required) is a type of number
  policy_dst_id = null
  # policy_src_id - (required) is a type of number
  policy_src_id = null
  # state_policy_srcdst_pos - (optional) is a type of string
  state_policy_srcdst_pos = null
}
```

[top](#index)

### Variables

```terraform
variable "alter_position" {
  description = "(required)"
  type        = string
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_state_checking" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "policy_dst_id" {
  description = "(required)"
  type        = number
}

variable "policy_src_id" {
  description = "(required)"
  type        = number
}

variable "state_policy_srcdst_pos" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_security_policyseq" "this" {
  alter_position          = var.alter_position
  comment                 = var.comment
  enable_state_checking   = var.enable_state_checking
  policy_dst_id           = var.policy_dst_id
  policy_src_id           = var.policy_src_id
  state_policy_srcdst_pos = var.state_policy_srcdst_pos
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewall_security_policyseq.this.id
}

output "state_policy_list" {
  description = "returns a list of object"
  value       = fortios_firewall_security_policyseq.this.state_policy_list
}

output "this" {
  value = fortios_firewall_security_policyseq.this
}
```

[top](#index)