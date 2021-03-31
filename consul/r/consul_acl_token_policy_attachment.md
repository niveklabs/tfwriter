# consul_acl_token_policy_attachment

[back](../consul.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    consul = ">= 2.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "consul_acl_token_policy_attachment" {
  source = "./modules/consul/r/consul_acl_token_policy_attachment"

  # policy - (required) is a type of string
  policy = null
  # token_id - (required) is a type of string
  token_id = null
}
```

[top](#index)

### Variables

```terraform
variable "policy" {
  description = "(required) - The policy name."
  type        = string
}

variable "token_id" {
  description = "(required) - The token accessor id."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "consul_acl_token_policy_attachment" "this" {
  policy   = var.policy
  token_id = var.token_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = consul_acl_token_policy_attachment.this.id
}

output "this" {
  value = consul_acl_token_policy_attachment.this
}
```

[top](#index)