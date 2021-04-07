# launchdarkly_team_member

[back](../launchdarkly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    launchdarkly = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "launchdarkly_team_member" {
  source = "./modules/launchdarkly/d/launchdarkly_team_member"

  # email - (required) is a type of string
  email = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "launchdarkly_team_member" "this" {
  # email - (required) is a type of string
  email = var.email
}
```

[top](#index)

### Outputs

```terraform
output "custom_roles" {
  description = "returns a set of string"
  value       = data.launchdarkly_team_member.this.custom_roles
}

output "first_name" {
  description = "returns a string"
  value       = data.launchdarkly_team_member.this.first_name
}

output "id" {
  description = "returns a string"
  value       = data.launchdarkly_team_member.this.id
}

output "last_name" {
  description = "returns a string"
  value       = data.launchdarkly_team_member.this.last_name
}

output "role" {
  description = "returns a string"
  value       = data.launchdarkly_team_member.this.role
}

output "this" {
  value = launchdarkly_team_member.this
}
```

[top](#index)