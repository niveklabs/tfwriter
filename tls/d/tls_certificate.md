# tls_certificate

[back](../tls.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tls_certificate" {
  source = "./modules/tls/d/tls_certificate"

  # url - (required) is a type of string
  url = null
  # verify_chain - (optional) is a type of bool
  verify_chain = null
}
```

[top](#index)

### Variables

```terraform
variable "url" {
  description = "(required)"
  type        = string
}

variable "verify_chain" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tls_certificate" "this" {
  # url - (required) is a type of string
  url = var.url
  # verify_chain - (optional) is a type of bool
  verify_chain = var.verify_chain
}
```

[top](#index)

### Outputs

```terraform
output "certificates" {
  description = "returns a list of object"
  value       = data.tls_certificate.this.certificates
}

output "id" {
  description = "returns a string"
  value       = data.tls_certificate.this.id
}

output "this" {
  value = tls_certificate.this
}
```

[top](#index)