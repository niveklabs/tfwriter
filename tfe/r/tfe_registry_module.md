# tfe_registry_module

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
module "tfe_registry_module" {
  source = "./modules/tfe/r/tfe_registry_module"


  vcs_repo = [{
    display_identifier = null
    identifier         = null
    oauth_token_id     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "vcs_repo" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      display_identifier = string
      identifier         = string
      oauth_token_id     = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tfe_registry_module" "this" {

  dynamic "vcs_repo" {
    for_each = var.vcs_repo
    content {
      display_identifier = vcs_repo.value["display_identifier"]
      identifier         = vcs_repo.value["identifier"]
      oauth_token_id     = vcs_repo.value["oauth_token_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_registry_module.this.id
}

output "module_provider" {
  description = "returns a string"
  value       = tfe_registry_module.this.module_provider
}

output "name" {
  description = "returns a string"
  value       = tfe_registry_module.this.name
}

output "organization" {
  description = "returns a string"
  value       = tfe_registry_module.this.organization
}

output "this" {
  value = tfe_registry_module.this
}
```

[top](#index)