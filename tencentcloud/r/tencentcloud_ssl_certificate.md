# tencentcloud_ssl_certificate

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
module "tencentcloud_ssl_certificate" {
  source = "./modules/tencentcloud/r/tencentcloud_ssl_certificate"

  # cert - (required) is a type of string
  cert = null
  # key - (optional) is a type of string
  key = null
  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of number
  project_id = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "cert" {
  description = "(required) - Content of the SSL certificate. Not allowed newline at the start and end."
  type        = string
}

variable "key" {
  description = "(optional) - Key of the SSL certificate and required when certificate type is `SVR`. Not allowed newline at the start and end."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the SSL certificate."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - Project ID of the SSL certificate. Default is `0`."
  type        = number
  default     = null
}

variable "type" {
  description = "(required) - Type of the SSL certificate. Valid values: `CA` and `SVR`."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_ssl_certificate" "this" {
  cert       = var.cert
  key        = var.key
  name       = var.name
  project_id = var.project_id
  type       = var.type
}
```

[top](#index)

### Outputs

```terraform
output "begin_time" {
  description = "returns a string"
  value       = tencentcloud_ssl_certificate.this.begin_time
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_ssl_certificate.this.create_time
}

output "domain" {
  description = "returns a string"
  value       = tencentcloud_ssl_certificate.this.domain
}

output "end_time" {
  description = "returns a string"
  value       = tencentcloud_ssl_certificate.this.end_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_ssl_certificate.this.id
}

output "product_zh_name" {
  description = "returns a string"
  value       = tencentcloud_ssl_certificate.this.product_zh_name
}

output "status" {
  description = "returns a number"
  value       = tencentcloud_ssl_certificate.this.status
}

output "subject_names" {
  description = "returns a list of string"
  value       = tencentcloud_ssl_certificate.this.subject_names
}

output "this" {
  value = tencentcloud_ssl_certificate.this
}
```

[top](#index)