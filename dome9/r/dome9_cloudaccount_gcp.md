# dome9_cloudaccount_gcp

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.21.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_cloudaccount_gcp" {
  source = "./modules/dome9/r/dome9_cloudaccount_gcp"

  # client_email - (required) is a type of string
  client_email = null
  # client_id - (required) is a type of string
  client_id = null
  # client_x509_cert_url - (required) is a type of string
  client_x509_cert_url = null
  # domain_name - (optional) is a type of string
  domain_name = null
  # gsuite_user - (optional) is a type of string
  gsuite_user = null
  # name - (required) is a type of string
  name = null
  # organizational_unit_id - (optional) is a type of string
  organizational_unit_id = null
  # private_key - (required) is a type of string
  private_key = null
  # private_key_id - (required) is a type of string
  private_key_id = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "client_email" {
  description = "(required)"
  type        = string
}

variable "client_id" {
  description = "(required)"
  type        = string
}

variable "client_x509_cert_url" {
  description = "(required)"
  type        = string
}

variable "domain_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gsuite_user" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "organizational_unit_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key" {
  description = "(required)"
  type        = string
}

variable "private_key_id" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "dome9_cloudaccount_gcp" "this" {
  # client_email - (required) is a type of string
  client_email = var.client_email
  # client_id - (required) is a type of string
  client_id = var.client_id
  # client_x509_cert_url - (required) is a type of string
  client_x509_cert_url = var.client_x509_cert_url
  # domain_name - (optional) is a type of string
  domain_name = var.domain_name
  # gsuite_user - (optional) is a type of string
  gsuite_user = var.gsuite_user
  # name - (required) is a type of string
  name = var.name
  # organizational_unit_id - (optional) is a type of string
  organizational_unit_id = var.organizational_unit_id
  # private_key - (required) is a type of string
  private_key = var.private_key
  # private_key_id - (required) is a type of string
  private_key_id = var.private_key_id
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dome9_cloudaccount_gcp.this.id
}

output "organizational_unit_name" {
  description = "returns a string"
  value       = dome9_cloudaccount_gcp.this.organizational_unit_name
}

output "organizational_unit_path" {
  description = "returns a string"
  value       = dome9_cloudaccount_gcp.this.organizational_unit_path
}

output "vendor" {
  description = "returns a string"
  value       = dome9_cloudaccount_gcp.this.vendor
}

output "this" {
  value = dome9_cloudaccount_gcp.this
}
```

[top](#index)