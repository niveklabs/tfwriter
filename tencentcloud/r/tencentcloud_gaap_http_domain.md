# tencentcloud_gaap_http_domain

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
module "tencentcloud_gaap_http_domain" {
  source = "./modules/tencentcloud/r/tencentcloud_gaap_http_domain"

  # basic_auth - (optional) is a type of bool
  basic_auth = null
  # basic_auth_id - (optional) is a type of string
  basic_auth_id = null
  # certificate_id - (optional) is a type of string
  certificate_id = null
  # client_certificate_id - (optional) is a type of string
  client_certificate_id = null
  # client_certificate_ids - (optional) is a type of set of string
  client_certificate_ids = []
  # domain - (required) is a type of string
  domain = null
  # gaap_auth - (optional) is a type of bool
  gaap_auth = null
  # gaap_auth_id - (optional) is a type of string
  gaap_auth_id = null
  # listener_id - (required) is a type of string
  listener_id = null
  # realserver_auth - (optional) is a type of bool
  realserver_auth = null
  # realserver_certificate_domain - (optional) is a type of string
  realserver_certificate_domain = null
  # realserver_certificate_id - (optional) is a type of string
  realserver_certificate_id = null
  # realserver_certificate_ids - (optional) is a type of set of string
  realserver_certificate_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "basic_auth" {
  description = "(optional) - Indicates whether basic authentication is enable, default value is `false`."
  type        = bool
  default     = null
}

variable "basic_auth_id" {
  description = "(optional) - ID of the basic authentication."
  type        = string
  default     = null
}

variable "certificate_id" {
  description = "(optional) - ID of the server certificate, default value is `default`."
  type        = string
  default     = null
}

variable "client_certificate_id" {
  description = "(optional) - ID of the client certificate, default value is `default`."
  type        = string
  default     = null
}

variable "client_certificate_ids" {
  description = "(optional) - ID list of the poly client certificate."
  type        = set(string)
  default     = null
}

variable "domain" {
  description = "(required) - Forward domain of the layer7 listener."
  type        = string
}

variable "gaap_auth" {
  description = "(optional) - Indicates whether SSL certificate authentication is enable, default value is `false`."
  type        = bool
  default     = null
}

variable "gaap_auth_id" {
  description = "(optional) - ID of the SSL certificate."
  type        = string
  default     = null
}

variable "listener_id" {
  description = "(required) - ID of the layer7 listener."
  type        = string
}

variable "realserver_auth" {
  description = "(optional) - Indicates whether realserver authentication is enable, default value is `false`."
  type        = bool
  default     = null
}

variable "realserver_certificate_domain" {
  description = "(optional) - CA certificate domain of the realserver."
  type        = string
  default     = null
}

variable "realserver_certificate_id" {
  description = "(optional) - CA certificate ID of the realserver."
  type        = string
  default     = null
}

variable "realserver_certificate_ids" {
  description = "(optional) - CA certificate ID list of the realserver."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_gaap_http_domain" "this" {
  # basic_auth - (optional) is a type of bool
  basic_auth = var.basic_auth
  # basic_auth_id - (optional) is a type of string
  basic_auth_id = var.basic_auth_id
  # certificate_id - (optional) is a type of string
  certificate_id = var.certificate_id
  # client_certificate_id - (optional) is a type of string
  client_certificate_id = var.client_certificate_id
  # client_certificate_ids - (optional) is a type of set of string
  client_certificate_ids = var.client_certificate_ids
  # domain - (required) is a type of string
  domain = var.domain
  # gaap_auth - (optional) is a type of bool
  gaap_auth = var.gaap_auth
  # gaap_auth_id - (optional) is a type of string
  gaap_auth_id = var.gaap_auth_id
  # listener_id - (required) is a type of string
  listener_id = var.listener_id
  # realserver_auth - (optional) is a type of bool
  realserver_auth = var.realserver_auth
  # realserver_certificate_domain - (optional) is a type of string
  realserver_certificate_domain = var.realserver_certificate_domain
  # realserver_certificate_id - (optional) is a type of string
  realserver_certificate_id = var.realserver_certificate_id
  # realserver_certificate_ids - (optional) is a type of set of string
  realserver_certificate_ids = var.realserver_certificate_ids
}
```

[top](#index)

### Outputs

```terraform
output "basic_auth_id" {
  description = "returns a string"
  value       = tencentcloud_gaap_http_domain.this.basic_auth_id
}

output "client_certificate_id" {
  description = "returns a string"
  value       = tencentcloud_gaap_http_domain.this.client_certificate_id
}

output "client_certificate_ids" {
  description = "returns a set of string"
  value       = tencentcloud_gaap_http_domain.this.client_certificate_ids
}

output "gaap_auth_id" {
  description = "returns a string"
  value       = tencentcloud_gaap_http_domain.this.gaap_auth_id
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_gaap_http_domain.this.id
}

output "realserver_certificate_domain" {
  description = "returns a string"
  value       = tencentcloud_gaap_http_domain.this.realserver_certificate_domain
}

output "realserver_certificate_id" {
  description = "returns a string"
  value       = tencentcloud_gaap_http_domain.this.realserver_certificate_id
}

output "realserver_certificate_ids" {
  description = "returns a set of string"
  value       = tencentcloud_gaap_http_domain.this.realserver_certificate_ids
}

output "this" {
  value = tencentcloud_gaap_http_domain.this
}
```

[top](#index)