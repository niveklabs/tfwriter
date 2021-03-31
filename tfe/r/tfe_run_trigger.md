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
    tfe = ">= 0.24.0"
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
  # workspace_id - (required) is a type of string
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

variable "workspace_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tfe_run_trigger" "this" {
  sourceable_id = var.sourceable_id
  workspace_id  = var.workspace_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_run_trigger.this.id
}

output "this" {
  value = tfe_run_trigger.this
}
```

[top](#index)