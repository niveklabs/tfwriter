# cloudflare_access_mutual_tls_certificate

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_access_mutual_tls_certificate" {
  source = "./modules/cloudflare/r/cloudflare_access_mutual_tls_certificate"

  # account_id - (optional) is a type of string
  account_id = null
  # associated_hostnames - (optional) is a type of list of string
  associated_hostnames = []
  # certificate - (optional) is a type of string
  certificate = null
  # name - (required) is a type of string
  name = null
  # zone_id - (optional) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "associated_hostnames" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_access_mutual_tls_certificate" "this" {
  # account_id - (optional) is a type of string
  account_id = var.account_id
  # associated_hostnames - (optional) is a type of list of string
  associated_hostnames = var.associated_hostnames
  # certificate - (optional) is a type of string
  certificate = var.certificate
  # name - (required) is a type of string
  name = var.name
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = cloudflare_access_mutual_tls_certificate.this.account_id
}

output "fingerprint" {
  description = "returns a string"
  value       = cloudflare_access_mutual_tls_certificate.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = cloudflare_access_mutual_tls_certificate.this.id
}

output "zone_id" {
  description = "returns a string"
  value       = cloudflare_access_mutual_tls_certificate.this.zone_id
}

output "this" {
  value = cloudflare_access_mutual_tls_certificate.this
}
```

[top](#index)