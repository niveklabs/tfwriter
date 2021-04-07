# thunder_fw_active_rule_set

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_fw_active_rule_set" {
  source = "./modules/thunder/r/thunder_fw_active_rule_set"

  # name - (optional) is a type of string
  name = null
  # override_nat_aging - (optional) is a type of number
  override_nat_aging = null
  # session_aging - (optional) is a type of string
  session_aging = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_nat_aging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "session_aging" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_fw_active_rule_set" "this" {
  # name - (optional) is a type of string
  name = var.name
  # override_nat_aging - (optional) is a type of number
  override_nat_aging = var.override_nat_aging
  # session_aging - (optional) is a type of string
  session_aging = var.session_aging
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_active_rule_set.this.id
}

output "this" {
  value = thunder_fw_active_rule_set.this
}
```

[top](#index)