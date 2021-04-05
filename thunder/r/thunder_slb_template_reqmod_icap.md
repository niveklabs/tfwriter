# thunder_slb_template_reqmod_icap

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_template_reqmod_icap" {
  source = "./modules/thunder/r/thunder_slb_template_reqmod_icap"

  # action - (optional) is a type of string
  action = null
  # allowed_http_methods - (optional) is a type of string
  allowed_http_methods = null
  # cylance - (optional) is a type of number
  cylance = null
  # disable_http_server_reset - (optional) is a type of number
  disable_http_server_reset = null
  # fail_close - (optional) is a type of number
  fail_close = null
  # include_protocol_in_uri - (optional) is a type of number
  include_protocol_in_uri = null
  # log_only_allowed_method - (optional) is a type of number
  log_only_allowed_method = null
  # logging - (optional) is a type of string
  logging = null
  # min_payload_size - (optional) is a type of number
  min_payload_size = null
  # name - (optional) is a type of string
  name = null
  # preview - (optional) is a type of number
  preview = null
  # server_ssl - (optional) is a type of string
  server_ssl = null
  # service_group - (optional) is a type of string
  service_group = null
  # service_url - (optional) is a type of string
  service_url = null
  # shared_partition_persist_source_ip_template - (optional) is a type of number
  shared_partition_persist_source_ip_template = null
  # shared_partition_tcp_proxy_template - (optional) is a type of number
  shared_partition_tcp_proxy_template = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # tcp_proxy - (optional) is a type of string
  tcp_proxy = null
  # template_persist_source_ip_shared - (optional) is a type of string
  template_persist_source_ip_shared = null
  # template_tcp_proxy_shared - (optional) is a type of string
  template_tcp_proxy_shared = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  bypass_ip_cfg = [{
    bypass_ip = null
    mask      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allowed_http_methods" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cylance" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "disable_http_server_reset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fail_close" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "include_protocol_in_uri" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "log_only_allowed_method" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "logging" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "min_payload_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preview" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server_ssl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shared_partition_persist_source_ip_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_tcp_proxy_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tcp_proxy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_persist_source_ip_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_tcp_proxy_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bypass_ip_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bypass_ip = string
      mask      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_reqmod_icap" "this" {
  action                                      = var.action
  allowed_http_methods                        = var.allowed_http_methods
  cylance                                     = var.cylance
  disable_http_server_reset                   = var.disable_http_server_reset
  fail_close                                  = var.fail_close
  include_protocol_in_uri                     = var.include_protocol_in_uri
  log_only_allowed_method                     = var.log_only_allowed_method
  logging                                     = var.logging
  min_payload_size                            = var.min_payload_size
  name                                        = var.name
  preview                                     = var.preview
  server_ssl                                  = var.server_ssl
  service_group                               = var.service_group
  service_url                                 = var.service_url
  shared_partition_persist_source_ip_template = var.shared_partition_persist_source_ip_template
  shared_partition_tcp_proxy_template         = var.shared_partition_tcp_proxy_template
  source_ip                                   = var.source_ip
  tcp_proxy                                   = var.tcp_proxy
  template_persist_source_ip_shared           = var.template_persist_source_ip_shared
  template_tcp_proxy_shared                   = var.template_tcp_proxy_shared
  user_tag                                    = var.user_tag
  uuid                                        = var.uuid

  dynamic "bypass_ip_cfg" {
    for_each = var.bypass_ip_cfg
    content {
      bypass_ip = bypass_ip_cfg.value["bypass_ip"]
      mask      = bypass_ip_cfg.value["mask"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_reqmod_icap.this.id
}

output "this" {
  value = thunder_slb_template_reqmod_icap.this
}
```

[top](#index)