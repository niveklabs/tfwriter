# okta_group_membership

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_group_membership" {
  source = "./modules/okta/r/okta_group_membership"

  # group_id - (required) is a type of string
  group_id = null
  # user_id - (required) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(required) - ID of a Okta Group"
  type        = string
}

variable "user_id" {
  description = "(required) - ID of a Okta User"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "okta_group_membership" "this" {
  # group_id - (required) is a type of string
  group_id = var.group_id
  # user_id - (required) is a type of string
  user_id = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_group_membership.this.id
}

output "this" {
  value = okta_group_membership.this
}
```

[top](#index)