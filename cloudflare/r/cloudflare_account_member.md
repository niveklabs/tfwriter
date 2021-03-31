# cloudflare_account_member

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_account_member" {
  source = "./modules/cloudflare/r/cloudflare_account_member"

  # email_address - (required) is a type of string
  email_address = null
  # role_ids - (required) is a type of set of string
  role_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "email_address" {
  description = "(required)"
  type        = string
}

variable "role_ids" {
  description = "(required)"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_account_member" "this" {
  email_address = var.email_address
  role_ids      = var.role_ids
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_account_member.this.id
}

output "this" {
  value = cloudflare_account_member.this
}
```

[top](#index)