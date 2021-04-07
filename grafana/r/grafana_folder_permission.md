# grafana_folder_permission

[back](../grafana.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    grafana = ">= 1.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "grafana_folder_permission" {
  source = "./modules/grafana/r/grafana_folder_permission"

  # folder_uid - (required) is a type of string
  folder_uid = null

  permissions = [{
    permission = null
    role       = null
    team_id    = null
    user_id    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "folder_uid" {
  description = "(required)"
  type        = string
}

variable "permissions" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      permission = string
      role       = string
      team_id    = number
      user_id    = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "grafana_folder_permission" "this" {
  # folder_uid - (required) is a type of string
  folder_uid = var.folder_uid

  dynamic "permissions" {
    for_each = var.permissions
    content {
      # permission - (required) is a type of string
      permission = permissions.value["permission"]
      # role - (optional) is a type of string
      role = permissions.value["role"]
      # team_id - (optional) is a type of number
      team_id = permissions.value["team_id"]
      # user_id - (optional) is a type of number
      user_id = permissions.value["user_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = grafana_folder_permission.this.id
}

output "this" {
  value = grafana_folder_permission.this
}
```

[top](#index)