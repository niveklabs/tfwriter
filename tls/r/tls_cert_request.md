# tls_cert_request

[back](../tls.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tls = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tls_cert_request" {
  source = "./modules/tls/r/tls_cert_request"

  # dns_names - (optional) is a type of list of string
  dns_names = []
  # ip_addresses - (optional) is a type of list of string
  ip_addresses = []
  # key_algorithm - (required) is a type of string
  key_algorithm = null
  # private_key_pem - (required) is a type of string
  private_key_pem = null
  # uris - (optional) is a type of list of string
  uris = []

  subject = [{
    common_name         = null
    country             = null
    locality            = null
    organization        = null
    organizational_unit = null
    postal_code         = null
    province            = null
    serial_number       = null
    street_address      = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dns_names" {
  description = "(optional) - List of DNS names to use as subjects of the certificate"
  type        = list(string)
  default     = null
}

variable "ip_addresses" {
  description = "(optional) - List of IP addresses to use as subjects of the certificate"
  type        = list(string)
  default     = null
}

variable "key_algorithm" {
  description = "(required) - Name of the algorithm to use to generate the certificate's private key"
  type        = string
}

variable "private_key_pem" {
  description = "(required) - PEM-encoded private key that the certificate will belong to"
  type        = string
}

variable "uris" {
  description = "(optional) - List of URIs to use as subjects of the certificate"
  type        = list(string)
  default     = null
}

variable "subject" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      common_name         = string
      country             = string
      locality            = string
      organization        = string
      organizational_unit = string
      postal_code         = string
      province            = string
      serial_number       = string
      street_address      = list(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tls_cert_request" "this" {
  # dns_names - (optional) is a type of list of string
  dns_names = var.dns_names
  # ip_addresses - (optional) is a type of list of string
  ip_addresses = var.ip_addresses
  # key_algorithm - (required) is a type of string
  key_algorithm = var.key_algorithm
  # private_key_pem - (required) is a type of string
  private_key_pem = var.private_key_pem
  # uris - (optional) is a type of list of string
  uris = var.uris

  dynamic "subject" {
    for_each = var.subject
    content {
      # common_name - (optional) is a type of string
      common_name = subject.value["common_name"]
      # country - (optional) is a type of string
      country = subject.value["country"]
      # locality - (optional) is a type of string
      locality = subject.value["locality"]
      # organization - (optional) is a type of string
      organization = subject.value["organization"]
      # organizational_unit - (optional) is a type of string
      organizational_unit = subject.value["organizational_unit"]
      # postal_code - (optional) is a type of string
      postal_code = subject.value["postal_code"]
      # province - (optional) is a type of string
      province = subject.value["province"]
      # serial_number - (optional) is a type of string
      serial_number = subject.value["serial_number"]
      # street_address - (optional) is a type of list of string
      street_address = subject.value["street_address"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cert_request_pem" {
  description = "returns a string"
  value       = tls_cert_request.this.cert_request_pem
}

output "id" {
  description = "returns a string"
  value       = tls_cert_request.this.id
}

output "this" {
  value = tls_cert_request.this
}
```

[top](#index)