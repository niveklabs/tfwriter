# vault_aws_secret_backend_role

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
module "vault_aws_secret_backend_role" {
  source = "./modules/vault/r/vault_aws_secret_backend_role"

  # backend - (required) is a type of string
  backend = null
  # credential_type - (required) is a type of string
  credential_type = null
  # default_sts_ttl - (optional) is a type of number
  default_sts_ttl = null
  # iam_groups - (optional) is a type of set of string
  iam_groups = []
  # max_sts_ttl - (optional) is a type of number
  max_sts_ttl = null
  # name - (required) is a type of string
  name = null
  # policy - (optional) is a type of string
  policy = null
  # policy_arn - (optional) is a type of string
  policy_arn = null
  # policy_arns - (optional) is a type of set of string
  policy_arns = []
  # policy_document - (optional) is a type of string
  policy_document = null
  # role_arns - (optional) is a type of set of string
  role_arns = []
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - The path of the AWS Secret Backend the role belongs to."
  type        = string
}

variable "credential_type" {
  description = "(required) - Role credential type."
  type        = string
}

variable "default_sts_ttl" {
  description = "(optional) - The default TTL in seconds for STS credentials. When a TTL is not specified when STS credentials are requested, and a default TTL is specified on the role, then this default TTL will be used. Valid only when credential_type is one of assumed_role or federation_token."
  type        = number
  default     = null
}

variable "iam_groups" {
  description = "(optional) - A list of IAM group names. IAM users generated against this vault role will be added to these IAM Groups. For a credential type of assumed_role or federation_token, the policies sent to the corresponding AWS call (sts:AssumeRole or sts:GetFederation) will be the policies from each group in iam_groups combined with the policy_document and policy_arns parameters."
  type        = set(string)
  default     = null
}

variable "max_sts_ttl" {
  description = "(optional) - The max allowed TTL in seconds for STS credentials (credentials TTL are capped to max_sts_ttl). Valid only when credential_type is one of assumed_role or federation_token."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Unique name for the role."
  type        = string
}

variable "policy" {
  description = "(optional) - IAM policy the role should use in JSON format."
  type        = string
  default     = null
}

variable "policy_arn" {
  description = "(optional) - ARN for an existing IAM policy the role should use."
  type        = string
  default     = null
}

variable "policy_arns" {
  description = "(optional) - ARN for an existing IAM policy the role should use."
  type        = set(string)
  default     = null
}

variable "policy_document" {
  description = "(optional) - IAM policy the role should use in JSON format."
  type        = string
  default     = null
}

variable "role_arns" {
  description = "(optional) - ARNs of AWS roles allowed to be assumed. Only valid when credential_type is 'assumed_role'"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_aws_secret_backend_role" "this" {
  # backend - (required) is a type of string
  backend = var.backend
  # credential_type - (required) is a type of string
  credential_type = var.credential_type
  # default_sts_ttl - (optional) is a type of number
  default_sts_ttl = var.default_sts_ttl
  # iam_groups - (optional) is a type of set of string
  iam_groups = var.iam_groups
  # max_sts_ttl - (optional) is a type of number
  max_sts_ttl = var.max_sts_ttl
  # name - (required) is a type of string
  name = var.name
  # policy - (optional) is a type of string
  policy = var.policy
  # policy_arn - (optional) is a type of string
  policy_arn = var.policy_arn
  # policy_arns - (optional) is a type of set of string
  policy_arns = var.policy_arns
  # policy_document - (optional) is a type of string
  policy_document = var.policy_document
  # role_arns - (optional) is a type of set of string
  role_arns = var.role_arns
}
```

[top](#index)

### Outputs

```terraform
output "default_sts_ttl" {
  description = "returns a number"
  value       = vault_aws_secret_backend_role.this.default_sts_ttl
}

output "id" {
  description = "returns a string"
  value       = vault_aws_secret_backend_role.this.id
}

output "max_sts_ttl" {
  description = "returns a number"
  value       = vault_aws_secret_backend_role.this.max_sts_ttl
}

output "this" {
  value = vault_aws_secret_backend_role.this
}
```

[top](#index)