# linode_token

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_token" {
  source = "./modules/linode/r/linode_token"

  # expiry - (optional) is a type of string
  expiry = null
  # label - (optional) is a type of string
  label = null
  # scopes - (required) is a type of string
  scopes = null
}
```

[top](#index)

### Variables

```terraform
variable "expiry" {
  description = "(optional) - When this token will expire. Personal Access Tokens cannot be renewed, so after this time the token will be completely unusable and a new token will need to be generated. Tokens may be created with 'null' as their expiry and will never expire unless revoked."
  type        = string
  default     = null
}

variable "label" {
  description = "(optional) - The label of the Linode Token."
  type        = string
  default     = null
}

variable "scopes" {
  description = "(required) - The scopes this token was created with. These define what parts of the Account the token can be used to access. Many command-line tools, such as the Linode CLI, require tokens with access to *. Tokens with more restrictive scopes are generally more secure."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "linode_token" "this" {
  expiry = var.expiry
  label  = var.label
  scopes = var.scopes
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = linode_token.this.created
}

output "id" {
  description = "returns a string"
  value       = linode_token.this.id
}

output "token" {
  description = "returns a string"
  value       = linode_token.this.token
  sensitive   = true
}

output "this" {
  value = linode_token.this
}
```

[top](#index)