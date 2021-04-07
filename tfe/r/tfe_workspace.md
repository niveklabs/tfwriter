# tfe_workspace

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
module "tfe_workspace" {
  source = "./modules/tfe/r/tfe_workspace"

  # agent_pool_id - (optional) is a type of string
  agent_pool_id = null
  # allow_destroy_plan - (optional) is a type of bool
  allow_destroy_plan = null
  # auto_apply - (optional) is a type of bool
  auto_apply = null
  # execution_mode - (optional) is a type of string
  execution_mode = null
  # file_triggers_enabled - (optional) is a type of bool
  file_triggers_enabled = null
  # name - (required) is a type of string
  name = null
  # operations - (optional) is a type of bool
  operations = null
  # organization - (required) is a type of string
  organization = null
  # queue_all_runs - (optional) is a type of bool
  queue_all_runs = null
  # speculative_enabled - (optional) is a type of bool
  speculative_enabled = null
  # ssh_key_id - (optional) is a type of string
  ssh_key_id = null
  # terraform_version - (optional) is a type of string
  terraform_version = null
  # trigger_prefixes - (optional) is a type of list of string
  trigger_prefixes = []
  # working_directory - (optional) is a type of string
  working_directory = null

  vcs_repo = [{
    branch             = null
    identifier         = null
    ingress_submodules = null
    oauth_token_id     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "agent_pool_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allow_destroy_plan" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_apply" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "execution_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_triggers_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "operations" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "organization" {
  description = "(required)"
  type        = string
}

variable "queue_all_runs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "speculative_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ssh_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "terraform_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trigger_prefixes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "working_directory" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcs_repo" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      branch             = string
      identifier         = string
      ingress_submodules = bool
      oauth_token_id     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tfe_workspace" "this" {
  # agent_pool_id - (optional) is a type of string
  agent_pool_id = var.agent_pool_id
  # allow_destroy_plan - (optional) is a type of bool
  allow_destroy_plan = var.allow_destroy_plan
  # auto_apply - (optional) is a type of bool
  auto_apply = var.auto_apply
  # execution_mode - (optional) is a type of string
  execution_mode = var.execution_mode
  # file_triggers_enabled - (optional) is a type of bool
  file_triggers_enabled = var.file_triggers_enabled
  # name - (required) is a type of string
  name = var.name
  # operations - (optional) is a type of bool
  operations = var.operations
  # organization - (required) is a type of string
  organization = var.organization
  # queue_all_runs - (optional) is a type of bool
  queue_all_runs = var.queue_all_runs
  # speculative_enabled - (optional) is a type of bool
  speculative_enabled = var.speculative_enabled
  # ssh_key_id - (optional) is a type of string
  ssh_key_id = var.ssh_key_id
  # terraform_version - (optional) is a type of string
  terraform_version = var.terraform_version
  # trigger_prefixes - (optional) is a type of list of string
  trigger_prefixes = var.trigger_prefixes
  # working_directory - (optional) is a type of string
  working_directory = var.working_directory

  dynamic "vcs_repo" {
    for_each = var.vcs_repo
    content {
      # branch - (optional) is a type of string
      branch = vcs_repo.value["branch"]
      # identifier - (required) is a type of string
      identifier = vcs_repo.value["identifier"]
      # ingress_submodules - (optional) is a type of bool
      ingress_submodules = vcs_repo.value["ingress_submodules"]
      # oauth_token_id - (required) is a type of string
      oauth_token_id = vcs_repo.value["oauth_token_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "execution_mode" {
  description = "returns a string"
  value       = tfe_workspace.this.execution_mode
}

output "external_id" {
  description = "returns a string"
  value       = tfe_workspace.this.external_id
}

output "id" {
  description = "returns a string"
  value       = tfe_workspace.this.id
}

output "operations" {
  description = "returns a bool"
  value       = tfe_workspace.this.operations
}

output "terraform_version" {
  description = "returns a string"
  value       = tfe_workspace.this.terraform_version
}

output "this" {
  value = tfe_workspace.this
}
```

[top](#index)