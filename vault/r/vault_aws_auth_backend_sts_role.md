# vault_aws_auth_backend_sts_role

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_aws_auth_backend_sts_role" {
  source = "./modules/vault/r/vault_aws_auth_backend_sts_role"

  # account_id - (required) is a type of string
  account_id = null
  # backend - (optional) is a type of string
  backend = null
  # sts_role - (required) is a type of string
  sts_role = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required) - AWS account ID to be associated with STS role."
  type        = string
}

variable "backend" {
  description = "(optional) - Unique name of the auth backend to configure."
  type        = string
  default     = null
}

variable "sts_role" {
  description = "(required) - AWS ARN for STS role to be assumed when interacting with the account specified."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_aws_auth_backend_sts_role" "this" {
  account_id = var.account_id
  backend    = var.backend
  sts_role   = var.sts_role
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_aws_auth_backend_sts_role.this.id
}

output "this" {
  value = vault_aws_auth_backend_sts_role.this
}
```

[top](#index)