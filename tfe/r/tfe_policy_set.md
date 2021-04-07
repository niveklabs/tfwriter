# tfe_policy_set

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
module "tfe_policy_set" {
  source = "./modules/tfe/r/tfe_policy_set"

  # description - (optional) is a type of string
  description = null
  # global - (optional) is a type of bool
  global = null
  # name - (required) is a type of string
  name = null
  # organization - (required) is a type of string
  organization = null
  # policies_path - (optional) is a type of string
  policies_path = null
  # policy_ids - (optional) is a type of set of string
  policy_ids = []
  # workspace_ids - (optional) is a type of set of string
  workspace_ids = []

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
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "global" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "organization" {
  description = "(required)"
  type        = string
}

variable "policies_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "workspace_ids" {
  description = "(optional)"
  type        = set(string)
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
resource "tfe_policy_set" "this" {
  # description - (optional) is a type of string
  description = var.description
  # global - (optional) is a type of bool
  global = var.global
  # name - (required) is a type of string
  name = var.name
  # organization - (required) is a type of string
  organization = var.organization
  # policies_path - (optional) is a type of string
  policies_path = var.policies_path
  # policy_ids - (optional) is a type of set of string
  policy_ids = var.policy_ids
  # workspace_ids - (optional) is a type of set of string
  workspace_ids = var.workspace_ids

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
output "description" {
  description = "returns a string"
  value       = tfe_policy_set.this.description
}

output "id" {
  description = "returns a string"
  value       = tfe_policy_set.this.id
}

output "this" {
  value = tfe_policy_set.this
}
```

[top](#index)