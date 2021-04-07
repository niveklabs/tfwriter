# tencentcloud_cdn_domains

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "tencentcloud_cdn_domains" {
  source = "./modules/tencentcloud/d/tencentcloud_cdn_domains"

  # domain - (optional) is a type of string
  domain = null
  # full_url_cache - (optional) is a type of bool
  full_url_cache = null
  # https_switch - (optional) is a type of string
  https_switch = null
  # origin_pull_protocol - (optional) is a type of string
  origin_pull_protocol = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # service_type - (optional) is a type of string
  service_type = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(optional) - Acceleration domain name."
  type        = string
  default     = null
}

variable "full_url_cache" {
  description = "(optional) - Whether to enable full-path cache."
  type        = bool
  default     = null
}

variable "https_switch" {
  description = "(optional) - HTTPS configuration. Valid values: `on`, `off` and `processing`."
  type        = string
  default     = null
}

variable "origin_pull_protocol" {
  description = "(optional) - Origin-pull protocol configuration. Valid values: `http`, `https` and `follow`."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "service_type" {
  description = "(optional) - Service type of acceleration domain name. The available value include `web`, `download` and `media`."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_cdn_domains" "this" {
  domain               = var.domain
  full_url_cache       = var.full_url_cache
  https_switch         = var.https_switch
  origin_pull_protocol = var.origin_pull_protocol
  result_output_file   = var.result_output_file
  service_type         = var.service_type
}
```

[top](#index)

### Outputs

```terraform
output "domain_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cdn_domains.this.domain_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cdn_domains.this.id
}

output "this" {
  value = tencentcloud_cdn_domains.this
}
```

[top](#index)