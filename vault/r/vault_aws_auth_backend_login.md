# vault_aws_auth_backend_login

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
module "vault_aws_auth_backend_login" {
  source = "./modules/vault/r/vault_aws_auth_backend_login"

  # backend - (optional) is a type of string
  backend = null
  # iam_http_request_method - (optional) is a type of string
  iam_http_request_method = null
  # iam_request_body - (optional) is a type of string
  iam_request_body = null
  # iam_request_headers - (optional) is a type of string
  iam_request_headers = null
  # iam_request_url - (optional) is a type of string
  iam_request_url = null
  # identity - (optional) is a type of string
  identity = null
  # nonce - (optional) is a type of string
  nonce = null
  # pkcs7 - (optional) is a type of string
  pkcs7 = null
  # role - (optional) is a type of string
  role = null
  # signature - (optional) is a type of string
  signature = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(optional) - AWS Auth Backend to read the token from."
  type        = string
  default     = null
}

variable "iam_http_request_method" {
  description = "(optional) - The HTTP method used in the signed request."
  type        = string
  default     = null
}

variable "iam_request_body" {
  description = "(optional) - The Base64-encoded body of the signed request."
  type        = string
  default     = null
}

variable "iam_request_headers" {
  description = "(optional) - The Base64-encoded, JSON serialized representation of the sts:GetCallerIdentity HTTP request headers."
  type        = string
  default     = null
}

variable "iam_request_url" {
  description = "(optional) - The Base64-encoded HTTP URL used in the signed request."
  type        = string
  default     = null
}

variable "identity" {
  description = "(optional) - Base64-encoded EC2 instance identity document to authenticate with."
  type        = string
  default     = null
}

variable "nonce" {
  description = "(optional) - The nonce to be used for subsequent login requests."
  type        = string
  default     = null
}

variable "pkcs7" {
  description = "(optional) - PKCS7 signature of the identity document to authenticate with, with all newline characters removed."
  type        = string
  default     = null
}

variable "role" {
  description = "(optional) - AWS Auth Role to read the token from."
  type        = string
  default     = null
}

variable "signature" {
  description = "(optional) - Base64-encoded SHA256 RSA signature of the instance identtiy document to authenticate with."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_aws_auth_backend_login" "this" {
  backend                 = var.backend
  iam_http_request_method = var.iam_http_request_method
  iam_request_body        = var.iam_request_body
  iam_request_headers     = var.iam_request_headers
  iam_request_url         = var.iam_request_url
  identity                = var.identity
  nonce                   = var.nonce
  pkcs7                   = var.pkcs7
  role                    = var.role
  signature               = var.signature
}
```

[top](#index)

### Outputs

```terraform
output "accessor" {
  description = "returns a string"
  value       = vault_aws_auth_backend_login.this.accessor
}

output "auth_type" {
  description = "returns a string"
  value       = vault_aws_auth_backend_login.this.auth_type
}

output "client_token" {
  description = "returns a string"
  value       = vault_aws_auth_backend_login.this.client_token
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = vault_aws_auth_backend_login.this.id
}

output "lease_duration" {
  description = "returns a number"
  value       = vault_aws_auth_backend_login.this.lease_duration
}

output "lease_start_time" {
  description = "returns a string"
  value       = vault_aws_auth_backend_login.this.lease_start_time
}

output "metadata" {
  description = "returns a map of string"
  value       = vault_aws_auth_backend_login.this.metadata
}

output "nonce" {
  description = "returns a string"
  value       = vault_aws_auth_backend_login.this.nonce
}

output "policies" {
  description = "returns a list of string"
  value       = vault_aws_auth_backend_login.this.policies
}

output "renewable" {
  description = "returns a bool"
  value       = vault_aws_auth_backend_login.this.renewable
}

output "role" {
  description = "returns a string"
  value       = vault_aws_auth_backend_login.this.role
}

output "this" {
  value = vault_aws_auth_backend_login.this
}
```

[top](#index)