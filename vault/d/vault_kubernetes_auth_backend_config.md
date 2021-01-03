# vault_kubernetes_auth_backend_config

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
    vault = ">= 2.17.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_kubernetes_auth_backend_config" {
  source = "./modules/vault/d/vault_kubernetes_auth_backend_config"

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
  # kubernetes_host - (optional) is a type of string
  kubernetes_host = null
  # pem_keys - (optional) is a type of list of string
  pem_keys = []
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
  description = "(optional) - Host must be a host string, a host:port pair, or a URL to the base of the Kubernetes API server."
  type        = string
  default     = null
}

variable "pem_keys" {
  description = "(optional) - Optional list of PEM-formatted public keys or certificates used to verify the signatures of Kubernetes service account JWTs. If a certificate is given, its public key will be extracted. Not every installation of Kubernetes exposes these keys."
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vault_kubernetes_auth_backend_config" "this" {
  backend                = var.backend
  disable_iss_validation = var.disable_iss_validation
  disable_local_ca_jwt   = var.disable_local_ca_jwt
  issuer                 = var.issuer
  kubernetes_ca_cert     = var.kubernetes_ca_cert
  kubernetes_host        = var.kubernetes_host
  pem_keys               = var.pem_keys
}
```

[top](#index)

### Outputs

```terraform
output "disable_iss_validation" {
  description = "returns a bool"
  value       = data.vault_kubernetes_auth_backend_config.this.disable_iss_validation
}

output "disable_local_ca_jwt" {
  description = "returns a bool"
  value       = data.vault_kubernetes_auth_backend_config.this.disable_local_ca_jwt
}

output "id" {
  description = "returns a string"
  value       = data.vault_kubernetes_auth_backend_config.this.id
}

output "issuer" {
  description = "returns a string"
  value       = data.vault_kubernetes_auth_backend_config.this.issuer
}

output "kubernetes_ca_cert" {
  description = "returns a string"
  value       = data.vault_kubernetes_auth_backend_config.this.kubernetes_ca_cert
}

output "kubernetes_host" {
  description = "returns a string"
  value       = data.vault_kubernetes_auth_backend_config.this.kubernetes_host
}

output "pem_keys" {
  description = "returns a list of string"
  value       = data.vault_kubernetes_auth_backend_config.this.pem_keys
}

output "this" {
  value = vault_kubernetes_auth_backend_config.this
}
```

[top](#index)