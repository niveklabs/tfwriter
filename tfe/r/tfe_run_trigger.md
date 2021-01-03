# tfe_run_trigger

[back](../tfe.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tfe = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tfe_run_trigger" {
  source = "./modules/tfe/r/tfe_run_trigger"

  # sourceable_id - (required) is a type of string
  sourceable_id = null
  # workspace_external_id - (optional) is a type of string
  workspace_external_id = null
  # workspace_id - (optional) is a type of string
  workspace_id = null
}
```

[top](#index)

### Variables

```terraform
variable "sourceable_id" {
  description = "(required)"
  type        = string
}

variable "workspace_external_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "workspace_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tfe_run_trigger" "this" {
  sourceable_id         = var.sourceable_id
  workspace_external_id = var.workspace_external_id
  workspace_id          = var.workspace_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_run_trigger.this.id
}

output "workspace_external_id" {
  description = "returns a string"
  value       = tfe_run_trigger.this.workspace_external_id
}

output "workspace_id" {
  description = "returns a string"
  value       = tfe_run_trigger.this.workspace_id
}

output "this" {
  value = tfe_run_trigger.this
}
```

[top](#index)