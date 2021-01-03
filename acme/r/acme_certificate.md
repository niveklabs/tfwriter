# acme_certificate

[back](../acme.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    acme = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "acme_certificate" {
  source = "./modules/acme/r/acme_certificate"

  # account_key_pem - (required) is a type of string
  account_key_pem = null
  # certificate_p12_password - (optional) is a type of string
  certificate_p12_password = null
  # certificate_request_pem - (optional) is a type of string
  certificate_request_pem = null
  # common_name - (optional) is a type of string
  common_name = null
  # disable_complete_propagation - (optional) is a type of bool
  disable_complete_propagation = null
  # key_type - (optional) is a type of string
  key_type = null
  # min_days_remaining - (optional) is a type of number
  min_days_remaining = null
  # must_staple - (optional) is a type of bool
  must_staple = null
  # pre_check_delay - (optional) is a type of number
  pre_check_delay = null
  # recursive_nameservers - (optional) is a type of list of string
  recursive_nameservers = []
  # subject_alternative_names - (optional) is a type of set of string
  subject_alternative_names = []

  dns_challenge = [{
    config   = {}
    provider = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_key_pem" {
  description = "(required)"
  type        = string
}

variable "certificate_p12_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate_request_pem" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "common_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_complete_propagation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "min_days_remaining" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "must_staple" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "pre_check_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "recursive_nameservers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "subject_alternative_names" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "dns_challenge" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      config   = map(string)
      provider = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "acme_certificate" "this" {
  account_key_pem              = var.account_key_pem
  certificate_p12_password     = var.certificate_p12_password
  certificate_request_pem      = var.certificate_request_pem
  common_name                  = var.common_name
  disable_complete_propagation = var.disable_complete_propagation
  key_type                     = var.key_type
  min_days_remaining           = var.min_days_remaining
  must_staple                  = var.must_staple
  pre_check_delay              = var.pre_check_delay
  recursive_nameservers        = var.recursive_nameservers
  subject_alternative_names    = var.subject_alternative_names

  dynamic "dns_challenge" {
    for_each = var.dns_challenge
    content {
      config   = dns_challenge.value["config"]
      provider = dns_challenge.value["provider"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "certificate_domain" {
  description = "returns a string"
  value       = acme_certificate.this.certificate_domain
}

output "certificate_p12" {
  description = "returns a string"
  value       = acme_certificate.this.certificate_p12
  sensitive   = true
}

output "certificate_pem" {
  description = "returns a string"
  value       = acme_certificate.this.certificate_pem
}

output "certificate_url" {
  description = "returns a string"
  value       = acme_certificate.this.certificate_url
}

output "id" {
  description = "returns a string"
  value       = acme_certificate.this.id
}

output "issuer_pem" {
  description = "returns a string"
  value       = acme_certificate.this.issuer_pem
}

output "private_key_pem" {
  description = "returns a string"
  value       = acme_certificate.this.private_key_pem
  sensitive   = true
}

output "this" {
  value = acme_certificate.this
}
```

[top](#index)