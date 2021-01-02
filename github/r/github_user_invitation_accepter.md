# github_user_invitation_accepter

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
module "github_user_invitation_accepter" {
  source = "./modules/github/r/github_user_invitation_accepter"

  # invitation_id - (required) is a type of string
  invitation_id = null
}
```

[top](#index)

### Variables

```terraform
variable "invitation_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "github_user_invitation_accepter" "this" {
  invitation_id = var.invitation_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = github_user_invitation_accepter.this.id
}

output "this" {
  value = github_user_invitation_accepter.this
}
```

[top](#index)