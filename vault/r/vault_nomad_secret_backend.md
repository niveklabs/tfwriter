# vault_nomad_secret_backend

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
module "vault_nomad_secret_backend" {
  source = "./modules/vault/r/vault_nomad_secret_backend"

  # address - (optional) is a type of string
  address = null
  # backend - (optional) is a type of string
  backend = null
  # ca_cert - (optional) is a type of string
  ca_cert = null
  # client_cert - (optional) is a type of string
  client_cert = null
  # client_key - (optional) is a type of string
  client_key = null
  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = null
  # description - (optional) is a type of string
  description = null
  # local - (optional) is a type of bool
  local = null
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = null
  # max_token_name_length - (optional) is a type of number
  max_token_name_length = null
  # max_ttl - (optional) is a type of number
  max_ttl = null
  # token - (optional) is a type of string
  token = null
  # ttl - (optional) is a type of number
  ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(optional) - Specifies the address of the Nomad instance, provided as \"protocol://host:port\" like \"http://127.0.0.1:4646\"."
  type        = string
  default     = null
}

variable "backend" {
  description = "(optional) - The mount path for the Nomad backend."
  type        = string
  default     = null
}

variable "ca_cert" {
  description = "(optional) - CA certificate to use when verifying Nomad server certificate, must be x509 PEM encoded."
  type        = string
  default     = null
}

variable "client_cert" {
  description = "(optional) - Client certificate used for Nomad's TLS communication, must be x509 PEM encoded and if this is set you need to also set client_key."
  type        = string
  default     = null
}

variable "client_key" {
  description = "(optional) - Client key used for Nomad's TLS communication, must be x509 PEM encoded and if this is set you need to also set client_cert."
  type        = string
  default     = null
}

variable "default_lease_ttl_seconds" {
  description = "(optional) - Default lease duration for secrets in seconds."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - Human-friendly description of the mount for the backend."
  type        = string
  default     = null
}

variable "local" {
  description = "(optional) - Mark the secrets engine as local-only. Local engines are not replicated or removed by replication. Tolerance duration to use when checking the last rotation time."
  type        = bool
  default     = null
}

variable "max_lease_ttl_seconds" {
  description = "(optional) - Maximum possible lease duration for secrets in seconds."
  type        = number
  default     = null
}

variable "max_token_name_length" {
  description = "(optional) - Specifies the maximum length to use for the name of the Nomad token generated with Generate Credential. If omitted, 0 is used and ignored, defaulting to the max value allowed by the Nomad version."
  type        = number
  default     = null
}

variable "max_ttl" {
  description = "(optional) - Maximum possible lease duration for secrets in seconds."
  type        = number
  default     = null
}

variable "token" {
  description = "(optional) - Specifies the Nomad Management token to use."
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional) - Maximum possible lease duration for secrets in seconds."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_nomad_secret_backend" "this" {
  # address - (optional) is a type of string
  address = var.address
  # backend - (optional) is a type of string
  backend = var.backend
  # ca_cert - (optional) is a type of string
  ca_cert = var.ca_cert
  # client_cert - (optional) is a type of string
  client_cert = var.client_cert
  # client_key - (optional) is a type of string
  client_key = var.client_key
  # default_lease_ttl_seconds - (optional) is a type of number
  default_lease_ttl_seconds = var.default_lease_ttl_seconds
  # description - (optional) is a type of string
  description = var.description
  # local - (optional) is a type of bool
  local = var.local
  # max_lease_ttl_seconds - (optional) is a type of number
  max_lease_ttl_seconds = var.max_lease_ttl_seconds
  # max_token_name_length - (optional) is a type of number
  max_token_name_length = var.max_token_name_length
  # max_ttl - (optional) is a type of number
  max_ttl = var.max_ttl
  # token - (optional) is a type of string
  token = var.token
  # ttl - (optional) is a type of number
  ttl = var.ttl
}
```

[top](#index)

### Outputs

```terraform
output "default_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_nomad_secret_backend.this.default_lease_ttl_seconds
}

output "id" {
  description = "returns a string"
  value       = vault_nomad_secret_backend.this.id
}

output "max_lease_ttl_seconds" {
  description = "returns a number"
  value       = vault_nomad_secret_backend.this.max_lease_ttl_seconds
}

output "max_token_name_length" {
  description = "returns a number"
  value       = vault_nomad_secret_backend.this.max_token_name_length
}

output "max_ttl" {
  description = "returns a number"
  value       = vault_nomad_secret_backend.this.max_ttl
}

output "ttl" {
  description = "returns a number"
  value       = vault_nomad_secret_backend.this.ttl
}

output "this" {
  value = vault_nomad_secret_backend.this
}
```

[top](#index)