# dome9_continuous_compliance_policy

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.20.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_continuous_compliance_policy" {
  source = "./modules/dome9/r/dome9_continuous_compliance_policy"

  # notification_ids - (required) is a type of list of string
  notification_ids = []
  # ruleset_id - (optional) is a type of number
  ruleset_id = null
  # target_id - (required) is a type of string
  target_id = null
  # target_type - (required) is a type of string
  target_type = null
}
```

[top](#index)

### Variables

```terraform
variable "notification_ids" {
  description = "(required)"
  type        = list(string)
}

variable "ruleset_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "target_id" {
  description = "(required)"
  type        = string
}

variable "target_type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "dome9_continuous_compliance_policy" "this" {
  notification_ids = var.notification_ids
  ruleset_id       = var.ruleset_id
  target_id        = var.target_id
  target_type      = var.target_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dome9_continuous_compliance_policy.this.id
}

output "this" {
  value = dome9_continuous_compliance_policy.this
}
```

[top](#index)