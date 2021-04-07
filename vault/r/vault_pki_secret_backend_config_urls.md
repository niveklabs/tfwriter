# vault_pki_secret_backend_config_urls

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
module "vault_pki_secret_backend_config_urls" {
  source = "./modules/vault/r/vault_pki_secret_backend_config_urls"

  # backend - (required) is a type of string
  backend = null
  # crl_distribution_points - (optional) is a type of list of string
  crl_distribution_points = []
  # issuing_certificates - (optional) is a type of list of string
  issuing_certificates = []
  # ocsp_servers - (optional) is a type of list of string
  ocsp_servers = []
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - The path of the PKI secret backend the resource belongs to."
  type        = string
}

variable "crl_distribution_points" {
  description = "(optional) - Specifies the URL values for the CRL Distribution Points field."
  type        = list(string)
  default     = null
}

variable "issuing_certificates" {
  description = "(optional) - Specifies the URL values for the Issuing Certificate field."
  type        = list(string)
  default     = null
}

variable "ocsp_servers" {
  description = "(optional) - Specifies the URL values for the OCSP Servers field."
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_pki_secret_backend_config_urls" "this" {
  # backend - (required) is a type of string
  backend = var.backend
  # crl_distribution_points - (optional) is a type of list of string
  crl_distribution_points = var.crl_distribution_points
  # issuing_certificates - (optional) is a type of list of string
  issuing_certificates = var.issuing_certificates
  # ocsp_servers - (optional) is a type of list of string
  ocsp_servers = var.ocsp_servers
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_pki_secret_backend_config_urls.this.id
}

output "this" {
  value = vault_pki_secret_backend_config_urls.this
}
```

[top](#index)