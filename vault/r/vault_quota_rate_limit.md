# vault_quota_rate_limit

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
module "vault_quota_rate_limit" {
  source = "./modules/vault/r/vault_quota_rate_limit"

  # name - (required) is a type of string
  name = null
  # path - (optional) is a type of string
  path = null
  # rate - (required) is a type of number
  rate = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the quota."
  type        = string
}

variable "path" {
  description = "(optional) - Path of the mount or namespace to apply the quota. A blank path configures a global rate limit quota."
  type        = string
  default     = null
}

variable "rate" {
  description = "(required) - The maximum number of requests at any given second to be allowed by the quota rule. The rate must be positive."
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "vault_quota_rate_limit" "this" {
  # name - (required) is a type of string
  name = var.name
  # path - (optional) is a type of string
  path = var.path
  # rate - (required) is a type of number
  rate = var.rate
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_quota_rate_limit.this.id
}

output "this" {
  value = vault_quota_rate_limit.this
}
```

[top](#index)