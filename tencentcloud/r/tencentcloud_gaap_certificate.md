# tencentcloud_gaap_certificate

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_gaap_certificate" {
  source = "./modules/tencentcloud/r/tencentcloud_gaap_certificate"

  # content - (required) is a type of string
  content = null
  # key - (optional) is a type of string
  key = null
  # name - (optional) is a type of string
  name = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "content" {
  description = "(required) - Content of the certificate, and URL encoding. When the certificate is basic authentication, use the `user:xxx password:xxx` format, where the password is encrypted with `htpasswd` or `openssl`; When the certificate is `CA` or `SSL`, the format is `pem`."
  type        = string
}

variable "key" {
  description = "(optional) - Key of the `SSL` certificate."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the certificate."
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - Type of the certificate. Valid value: `BASIC`, `CLIENT`, `SERVER`, `REALSERVER` and `PROXY`. `BASIC` means basic certificate; `CLIENT` means client CA certificate; `SERVER` means server SSL certificate; `REALSERVER` means realserver CA certificate; `PROXY` means proxy SSL certificate."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_gaap_certificate" "this" {
  content = var.content
  key     = var.key
  name    = var.name
  type    = var.type
}
```

[top](#index)

### Outputs

```terraform
output "begin_time" {
  description = "returns a string"
  value       = tencentcloud_gaap_certificate.this.begin_time
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_gaap_certificate.this.create_time
}

output "end_time" {
  description = "returns a string"
  value       = tencentcloud_gaap_certificate.this.end_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_gaap_certificate.this.id
}

output "issuer_cn" {
  description = "returns a string"
  value       = tencentcloud_gaap_certificate.this.issuer_cn
}

output "subject_cn" {
  description = "returns a string"
  value       = tencentcloud_gaap_certificate.this.subject_cn
}

output "this" {
  value = tencentcloud_gaap_certificate.this
}
```

[top](#index)