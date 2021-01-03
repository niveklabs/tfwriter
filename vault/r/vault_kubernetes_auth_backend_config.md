# vault_kubernetes_auth_backend_config

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
    vault = ">= 2.17.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_kubernetes_auth_backend_config" {
  source = "./modules/vault/r/vault_kubernetes_auth_backend_config"

  # backend - (optional) is a type of string
  backend = null
  # disable_iss_validation - (optional) is a type of bool
  disable_iss_validation = null
  # disable_local_ca_jwt - (optional) is a type of bool
  disable_local_ca_jwt = null
  # issuer - (optional) is a type of string
  issuer = null
  # kubernetes_ca_cert - (optional) is a type of string
  kubernetes_ca_cert = null
  # kubernetes_host - (required) is a type of string
  kubernetes_host = null
  # pem_keys - (optional) is a type of list of string
  pem_keys = []
  # token_reviewer_jwt - (optional) is a type of string
  token_reviewer_jwt = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(optional) - Unique name of the kubernetes backend to configure."
  type        = string
  default     = null
}

variable "disable_iss_validation" {
  description = "(optional) - Optional disable JWT issuer validation. Allows to skip ISS validation."
  type        = bool
  default     = null
}

variable "disable_local_ca_jwt" {
  description = "(optional) - Optional disable defaulting to the local CA cert and service account JWT when running in a Kubernetes pod."
  type        = bool
  default     = null
}

variable "issuer" {
  description = "(optional) - Optional JWT issuer. If no issuer is specified, kubernetes.io/serviceaccount will be used as the default issuer."
  type        = string
  default     = null
}

variable "kubernetes_ca_cert" {
  description = "(optional) - PEM encoded CA cert for use by the TLS client used to talk with the Kubernetes API."
  type        = string
  default     = null
}

variable "kubernetes_host" {
  description = "(required) - Host must be a host string, a host:port pair, or a URL to the base of the Kubernetes API server."
  type        = string
}

variable "pem_keys" {
  description = "(optional) - Optional list of PEM-formatted public keys or certificates used to verify the signatures of Kubernetes service account JWTs. If a certificate is given, its public key will be extracted. Not every installation of Kubernetes exposes these keys."
  type        = list(string)
  default     = null
}

variable "token_reviewer_jwt" {
  description = "(optional) - A service account JWT used to access the TokenReview API to validate other JWTs during login. If not set the JWT used for login will be used to access the API."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_kubernetes_auth_backend_config" "this" {
  backend                = var.backend
  disable_iss_validation = var.disable_iss_validation
  disable_local_ca_jwt   = var.disable_local_ca_jwt
  issuer                 = var.issuer
  kubernetes_ca_cert     = var.kubernetes_ca_cert
  kubernetes_host        = var.kubernetes_host
  pem_keys               = var.pem_keys
  token_reviewer_jwt     = var.token_reviewer_jwt
}
```

[top](#index)

### Outputs

```terraform
output "disable_iss_validation" {
  description = "returns a bool"
  value       = vault_kubernetes_auth_backend_config.this.disable_iss_validation
}

output "disable_local_ca_jwt" {
  description = "returns a bool"
  value       = vault_kubernetes_auth_backend_config.this.disable_local_ca_jwt
}

output "id" {
  description = "returns a string"
  value       = vault_kubernetes_auth_backend_config.this.id
}

output "this" {
  value = vault_kubernetes_auth_backend_config.this
}
```

[top](#index)