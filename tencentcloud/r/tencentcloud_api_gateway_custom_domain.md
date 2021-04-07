# tencentcloud_api_gateway_custom_domain

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
module "tencentcloud_api_gateway_custom_domain" {
  source = "./modules/tencentcloud/r/tencentcloud_api_gateway_custom_domain"

  # certificate_id - (optional) is a type of string
  certificate_id = null
  # default_domain - (required) is a type of string
  default_domain = null
  # is_default_mapping - (optional) is a type of bool
  is_default_mapping = null
  # net_type - (required) is a type of string
  net_type = null
  # path_mappings - (optional) is a type of set of string
  path_mappings = []
  # protocol - (required) is a type of string
  protocol = null
  # service_id - (required) is a type of string
  service_id = null
  # sub_domain - (required) is a type of string
  sub_domain = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_id" {
  description = "(optional) - Unique certificate ID of the custom domain name to be bound. You can choose to upload for the `protocol` attribute value `https` or `http&https`."
  type        = string
  default     = null
}

variable "default_domain" {
  description = "(required) - Default domain name."
  type        = string
}

variable "is_default_mapping" {
  description = "(optional) - Whether the default path mapping is used. The default value is `true`. When it is `false`, it means custom path mapping. In this case, the `path_mappings` attribute is required."
  type        = bool
  default     = null
}

variable "net_type" {
  description = "(required) - Network type. Valid values: `OUTER`, `INNER`."
  type        = string
}

variable "path_mappings" {
  description = "(optional) - Custom domain name path mapping. The data format is: `path#environment`. Optional values for the environment are `test`, `prepub`, and `release`."
  type        = set(string)
  default     = null
}

variable "protocol" {
  description = "(required) - Protocol supported by service. Valid values: `http`, `https`, `http&https`."
  type        = string
}

variable "service_id" {
  description = "(required) - Unique service ID."
  type        = string
}

variable "sub_domain" {
  description = "(required) - Custom domain name to be bound."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_api_gateway_custom_domain" "this" {
  certificate_id     = var.certificate_id
  default_domain     = var.default_domain
  is_default_mapping = var.is_default_mapping
  net_type           = var.net_type
  path_mappings      = var.path_mappings
  protocol           = var.protocol
  service_id         = var.service_id
  sub_domain         = var.sub_domain
}
```

[top](#index)

### Outputs

```terraform
output "certificate_id" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_custom_domain.this.certificate_id
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_api_gateway_custom_domain.this.id
}

output "path_mappings" {
  description = "returns a set of string"
  value       = tencentcloud_api_gateway_custom_domain.this.path_mappings
}

output "status" {
  description = "returns a number"
  value       = tencentcloud_api_gateway_custom_domain.this.status
}

output "this" {
  value = tencentcloud_api_gateway_custom_domain.this
}
```

[top](#index)