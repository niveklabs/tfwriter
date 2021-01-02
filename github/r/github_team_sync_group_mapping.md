# github_team_sync_group_mapping

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    github = ">= 4.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "github_team_sync_group_mapping" {
  source = "./modules/github/r/github_team_sync_group_mapping"

  # team_slug - (required) is a type of string
  team_slug = null

  group = [{
    group_description = null
    group_id          = null
    group_name        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "team_slug" {
  description = "(required)"
  type        = string
}

variable "group" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      group_description = string
      group_id          = string
      group_name        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "github_team_sync_group_mapping" "this" {
  team_slug = var.team_slug

  dynamic "group" {
    for_each = var.group
    content {
      group_description = group.value["group_description"]
      group_id          = group.value["group_id"]
      group_name        = group.value["group_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = github_team_sync_group_mapping.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_team_sync_group_mapping.this.id
}

output "this" {
  value = github_team_sync_group_mapping.this
}
```

[top](#index)