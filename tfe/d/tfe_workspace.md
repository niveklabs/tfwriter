# tfe_workspace

[back](../tfe.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tfe_workspace" {
  source = "./modules/tfe/d/tfe_workspace"

  # name - (required) is a type of string
  name = null
  # organization - (required) is a type of string
  organization = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "organization" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "tfe_workspace" "this" {
  # name - (required) is a type of string
  name = var.name
  # organization - (required) is a type of string
  organization = var.organization
}
```

[top](#index)

### Outputs

```terraform
output "allow_destroy_plan" {
  description = "returns a bool"
  value       = data.tfe_workspace.this.allow_destroy_plan
}

output "auto_apply" {
  description = "returns a bool"
  value       = data.tfe_workspace.this.auto_apply
}

output "external_id" {
  description = "returns a string"
  value       = data.tfe_workspace.this.external_id
}

output "file_triggers_enabled" {
  description = "returns a bool"
  value       = data.tfe_workspace.this.file_triggers_enabled
}

output "id" {
  description = "returns a string"
  value       = data.tfe_workspace.this.id
}

output "operations" {
  description = "returns a bool"
  value       = data.tfe_workspace.this.operations
}

output "queue_all_runs" {
  description = "returns a bool"
  value       = data.tfe_workspace.this.queue_all_runs
}

output "speculative_enabled" {
  description = "returns a bool"
  value       = data.tfe_workspace.this.speculative_enabled
}

output "ssh_key_id" {
  description = "returns a string"
  value       = data.tfe_workspace.this.ssh_key_id
}

output "terraform_version" {
  description = "returns a string"
  value       = data.tfe_workspace.this.terraform_version
}

output "trigger_prefixes" {
  description = "returns a list of string"
  value       = data.tfe_workspace.this.trigger_prefixes
}

output "vcs_repo" {
  description = "returns a list of object"
  value       = data.tfe_workspace.this.vcs_repo
}

output "working_directory" {
  description = "returns a string"
  value       = data.tfe_workspace.this.working_directory
}

output "this" {
  value = tfe_workspace.this
}
```

[top](#index)