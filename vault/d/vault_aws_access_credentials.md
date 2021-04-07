# vault_aws_access_credentials

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "vault_aws_access_credentials" {
  source = "./modules/vault/d/vault_aws_access_credentials"

  # backend - (required) is a type of string
  backend = null
  # region - (optional) is a type of string
  region = null
  # role - (required) is a type of string
  role = null
  # role_arn - (optional) is a type of string
  role_arn = null
  # ttl - (optional) is a type of string
  ttl = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - AWS Secret Backend to read credentials from."
  type        = string
}

variable "region" {
  description = "(optional) - Region the read credentials belong to."
  type        = string
  default     = null
}

variable "role" {
  description = "(required) - AWS Secret Role to read credentials from."
  type        = string
}

variable "role_arn" {
  description = "(optional) - ARN to use if multiple are available in the role. Required if the role has multiple ARNs."
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional) - User specified Time-To-Live for the STS token. Uses the Role defined default_sts_ttl when not specified"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Type of credentials to read. Must be either 'creds' for Access Key and Secret Key, or 'sts' for STS."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vault_aws_access_credentials" "this" {
  # backend - (required) is a type of string
  backend = var.backend
  # region - (optional) is a type of string
  region = var.region
  # role - (required) is a type of string
  role = var.role
  # role_arn - (optional) is a type of string
  role_arn = var.role_arn
  # ttl - (optional) is a type of string
  ttl = var.ttl
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "access_key" {
  description = "returns a string"
  value       = data.vault_aws_access_credentials.this.access_key
}

output "id" {
  description = "returns a string"
  value       = data.vault_aws_access_credentials.this.id
}

output "lease_duration" {
  description = "returns a number"
  value       = data.vault_aws_access_credentials.this.lease_duration
}

output "lease_id" {
  description = "returns a string"
  value       = data.vault_aws_access_credentials.this.lease_id
}

output "lease_renewable" {
  description = "returns a bool"
  value       = data.vault_aws_access_credentials.this.lease_renewable
}

output "lease_start_time" {
  description = "returns a string"
  value       = data.vault_aws_access_credentials.this.lease_start_time
}

output "secret_key" {
  description = "returns a string"
  value       = data.vault_aws_access_credentials.this.secret_key
}

output "security_token" {
  description = "returns a string"
  value       = data.vault_aws_access_credentials.this.security_token
}

output "this" {
  value = vault_aws_access_credentials.this
}
```

[top](#index)