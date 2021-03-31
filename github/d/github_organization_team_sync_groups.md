# github_organization_team_sync_groups

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    github = ">= 4.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "github_organization_team_sync_groups" {
  source = "./modules/github/d/github_organization_team_sync_groups"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "github_organization_team_sync_groups" "this" {
}
```

[top](#index)

### Outputs

```terraform
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