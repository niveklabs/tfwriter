# github_organization_team_sync_groups

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    github = ">= 4.1.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "github_organization_team_sync_groups" {
  source = "./modules/github/d/github_organization_team_sync_groups"

}
```

[top](#index)

### Variables

```hcl
```

[top](#index)

### Datasource

```hcl
data "github_organization_team_sync_groups" "this" {
}
```

[top](#index)

### Outputs

```hcl
output "groups" {
  description = "returns a list of object"
  value       = data.github_organization_team_sync_groups.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.github_organization_team_sync_groups.this.id
}

output "this" {
  value = github_organization_team_sync_groups.this
}
```

[top](#index)