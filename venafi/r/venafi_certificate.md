# venafi_certificate

[back](../venafi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    venafi = ">= 0.11.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "venafi_certificate" {
  source = "./modules/venafi/r/venafi_certificate"

  # algorithm - (optional) is a type of string
  algorithm = null
  # certificate_dn - (optional) is a type of string
  certificate_dn = null
  # common_name - (required) is a type of string
  common_name = null
  # csr_pem - (optional) is a type of string
  csr_pem = null
  # custom_fields - (optional) is a type of map of string
  custom_fields = {}
  # ecdsa_curve - (optional) is a type of string
  ecdsa_curve = null
  # expiration_window - (optional) is a type of number
  expiration_window = null
  # issuer_hint - (optional) is a type of string
  issuer_hint = null
  # key_password - (optional) is a type of string
  key_password = null
  # pkcs12 - (optional) is a type of string
  pkcs12 = null
  # private_key_pem - (optional) is a type of string
  private_key_pem = null
  # rsa_bits - (optional) is a type of number
  rsa_bits = null
  # san_dns - (optional) is a type of list of string
  san_dns = []
  # san_email - (optional) is a type of list of string
  san_email = []
  # san_ip - (optional) is a type of list of string
  san_ip = []
  # valid_days - (optional) is a type of number
  valid_days = null
}
```

[top](#index)

### Variables

```terraform
variable "algorithm" {
  description = "(optional) - Key encryption algorithm. RSA or ECDSA. RSA is default."
  type        = string
  default     = null
}

variable "certificate_dn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "common_name" {
  description = "(required) - Common name of certificate"
  type        = string
}

variable "csr_pem" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_fields" {
  description = "(optional) - Data map in the form key=\"value1|value2|...|valueN\", to be added to the certificate"
  type        = map(string)
  default     = null
}

variable "ecdsa_curve" {
  description = "(optional) - ECDSA curve to use when generating a key"
  type        = string
  default     = null
}

variable "expiration_window" {
  description = "(optional) - Number of hours before the certificates expiry when a new certificate will be generated"
  type        = number
  default     = null
}

variable "issuer_hint" {
  description = "(optional) - Indicate the target issuer to enable valid days with Venafi Platform; DigiCert, Entrust, and Microsoft are supported values."
  type        = string
  default     = null
}

variable "key_password" {
  description = "(optional) - Private key password."
  type        = string
  default     = null
}

variable "pkcs12" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key_pem" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rsa_bits" {
  description = "(optional) - Number of bits to use when generating an RSA key"
  type        = number
  default     = null
}

variable "san_dns" {
  description = "(optional) - List of DNS names to use as subjects of the certificate"
  type        = list(string)
  default     = null
}

variable "san_email" {
  description = "(optional) - List of email addresses to use as subjects of the certificate"
  type        = list(string)
  default     = null
}

variable "san_ip" {
  description = "(optional) - List of IP addresses to use as subjects of the certificate"
  type        = list(string)
  default     = null
}

variable "valid_days" {
  description = "(optional) - The desired certificate validity"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "venafi_certificate" "this" {
  # algorithm - (optional) is a type of string
  algorithm = var.algorithm
  # certificate_dn - (optional) is a type of string
  certificate_dn = var.certificate_dn
  # common_name - (required) is a type of string
  common_name = var.common_name
  # csr_pem - (optional) is a type of string
  csr_pem = var.csr_pem
  # custom_fields - (optional) is a type of map of string
  custom_fields = var.custom_fields
  # ecdsa_curve - (optional) is a type of string
  ecdsa_curve = var.ecdsa_curve
  # expiration_window - (optional) is a type of number
  expiration_window = var.expiration_window
  # issuer_hint - (optional) is a type of string
  issuer_hint = var.issuer_hint
  # key_password - (optional) is a type of string
  key_password = var.key_password
  # pkcs12 - (optional) is a type of string
  pkcs12 = var.pkcs12
  # private_key_pem - (optional) is a type of string
  private_key_pem = var.private_key_pem
  # rsa_bits - (optional) is a type of number
  rsa_bits = var.rsa_bits
  # san_dns - (optional) is a type of list of string
  san_dns = var.san_dns
  # san_email - (optional) is a type of list of string
  san_email = var.san_email
  # san_ip - (optional) is a type of list of string
  san_ip = var.san_ip
  # valid_days - (optional) is a type of number
  valid_days = var.valid_days
}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = venafi_certificate.this.certificate
}

output "certificate_dn" {
  description = "returns a string"
  value       = venafi_certificate.this.certificate_dn
}

output "chain" {
  description = "returns a string"
  value       = venafi_certificate.this.chain
}

output "csr_pem" {
  description = "returns a string"
  value       = venafi_certificate.this.csr_pem
}

output "id" {
  description = "returns a string"
  value       = venafi_certificate.this.id
}

output "pkcs12" {
  description = "returns a string"
  value       = venafi_certificate.this.pkcs12
}

output "private_key_pem" {
  description = "returns a string"
  value       = venafi_certificate.this.private_key_pem
  sensitive   = true
}

output "this" {
  value = venafi_certificate.this
}
```

[top](#index)