# vault_aws_auth_backend_cert

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
module "vault_aws_auth_backend_cert" {
  source = "./modules/vault/r/vault_aws_auth_backend_cert"

  # aws_public_cert - (required) is a type of string
  aws_public_cert = null
  # backend - (optional) is a type of string
  backend = null
  # cert_name - (required) is a type of string
  cert_name = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "aws_public_cert" {
  description = "(required) - Base64 encoded AWS Public key required to verify PKCS7 signature of the EC2 instance metadata."
  type        = string
}

variable "backend" {
  description = "(optional) - Unique name of the auth backend to configure."
  type        = string
  default     = null
}

variable "cert_name" {
  description = "(required) - Name of the certificate to configure."
  type        = string
}

variable "type" {
  description = "(optional) - The type of document that can be verified using the certificate. Must be either \"pkcs7\" or \"identity\"."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_aws_auth_backend_cert" "this" {
  aws_public_cert = var.aws_public_cert
  backend         = var.backend
  cert_name       = var.cert_name
  type            = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_aws_auth_backend_cert.this.id
}

output "this" {
  value = vault_aws_auth_backend_cert.this
}
```

[top](#index)