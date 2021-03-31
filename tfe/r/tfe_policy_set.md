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
  description   = var.description
  global        = var.global
  name          = var.name
  organization  = var.organization
  policies_path = var.policies_path
  policy_ids    = var.policy_ids
  workspace_ids = var.workspace_ids

  dynamic "vcs_repo" {
    for_each = var.vcs_repo
    content {
      branch             = vcs_repo.value["branch"]
      identifier         = vcs_repo.value["identifier"]
      ingress_submodules = vcs_repo.value["ingress_submodules"]
      oauth_token_id     = vcs_repo.value["oauth_token_id"]
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