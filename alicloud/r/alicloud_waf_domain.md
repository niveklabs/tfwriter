# alicloud_waf_domain

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_waf_domain" {
  source = "./modules/alicloud/r/alicloud_waf_domain"

  # cluster_type - (optional) is a type of string
  cluster_type = null
  # connection_time - (optional) is a type of number
  connection_time = null
  # domain - (optional) is a type of string
  domain = null
  # domain_name - (optional) is a type of string
  domain_name = null
  # http2_port - (optional) is a type of set of string
  http2_port = []
  # http_port - (optional) is a type of set of string
  http_port = []
  # http_to_user_ip - (optional) is a type of string
  http_to_user_ip = null
  # https_port - (optional) is a type of set of string
  https_port = []
  # https_redirect - (optional) is a type of string
  https_redirect = null
  # instance_id - (required) is a type of string
  instance_id = null
  # is_access_product - (required) is a type of string
  is_access_product = null
  # load_balancing - (optional) is a type of string
  load_balancing = null
  # read_time - (optional) is a type of number
  read_time = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # source_ips - (optional) is a type of set of string
  source_ips = []
  # write_time - (optional) is a type of number
  write_time = null

  log_headers = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "connection_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http2_port" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "http_port" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "http_to_user_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "https_port" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "https_redirect" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "is_access_product" {
  description = "(required)"
  type        = string
}

variable "load_balancing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "read_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ips" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "write_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "log_headers" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_waf_domain" "this" {
  cluster_type      = var.cluster_type
  connection_time   = var.connection_time
  domain            = var.domain
  domain_name       = var.domain_name
  http2_port        = var.http2_port
  http_port         = var.http_port
  http_to_user_ip   = var.http_to_user_ip
  https_port        = var.https_port
  https_redirect    = var.https_redirect
  instance_id       = var.instance_id
  is_access_product = var.is_access_product
  load_balancing    = var.load_balancing
  read_time         = var.read_time
  resource_group_id = var.resource_group_id
  source_ips        = var.source_ips
  write_time        = var.write_time

  dynamic "log_headers" {
    for_each = var.log_headers
    content {
      key   = log_headers.value["key"]
      value = log_headers.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cname" {
  description = "returns a string"
  value       = alicloud_waf_domain.this.cname
}

output "domain" {
  description = "returns a string"
  value       = alicloud_waf_domain.this.domain
}

output "domain_name" {
  description = "returns a string"
  value       = alicloud_waf_domain.this.domain_name
}

output "id" {
  description = "returns a string"
  value       = alicloud_waf_domain.this.id
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_waf_domain.this.resource_group_id
}

output "this" {
  value = alicloud_waf_domain.this
}
```

[top](#index)