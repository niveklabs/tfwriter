# thunder_slb_template_external_service

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
module "thunder_slb_template_external_service" {
  source = "./modules/thunder/r/thunder_slb_template_external_service"

  # action - (optional) is a type of string
  action = null
  # failure_action - (optional) is a type of string
  failure_action = null
  # name - (optional) is a type of string
  name = null
  # service_group - (optional) is a type of string
  service_group = null
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
  # timeout - (optional) is a type of number
  timeout = null
  # type - (optional) is a type of string
  type = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  bypass_ip_cfg = [{
    bypass_ip = null
    mask      = null
  }]

  request_header_forward_list = [{
    request_header_forward = null
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

variable "failure_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_group" {
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

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
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

variable "request_header_forward_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      request_header_forward = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_external_service" "this" {
  # action - (optional) is a type of string
  action = var.action
  # failure_action - (optional) is a type of string
  failure_action = var.failure_action
  # name - (optional) is a type of string
  name = var.name
  # service_group - (optional) is a type of string
  service_group = var.service_group
  # shared_partition_persist_source_ip_template - (optional) is a type of number
  shared_partition_persist_source_ip_template = var.shared_partition_persist_source_ip_template
  # shared_partition_tcp_proxy_template - (optional) is a type of number
  shared_partition_tcp_proxy_template = var.shared_partition_tcp_proxy_template
  # source_ip - (optional) is a type of string
  source_ip = var.source_ip
  # tcp_proxy - (optional) is a type of string
  tcp_proxy = var.tcp_proxy
  # template_persist_source_ip_shared - (optional) is a type of string
  template_persist_source_ip_shared = var.template_persist_source_ip_shared
  # template_tcp_proxy_shared - (optional) is a type of string
  template_tcp_proxy_shared = var.template_tcp_proxy_shared
  # timeout - (optional) is a type of number
  timeout = var.timeout
  # type - (optional) is a type of string
  type = var.type
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "bypass_ip_cfg" {
    for_each = var.bypass_ip_cfg
    content {
      # bypass_ip - (optional) is a type of string
      bypass_ip = bypass_ip_cfg.value["bypass_ip"]
      # mask - (optional) is a type of string
      mask = bypass_ip_cfg.value["mask"]
    }
  }

  dynamic "request_header_forward_list" {
    for_each = var.request_header_forward_list
    content {
      # request_header_forward - (optional) is a type of string
      request_header_forward = request_header_forward_list.value["request_header_forward"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_external_service.this.id
}

output "this" {
  value = thunder_slb_template_external_service.this
}
```

[top](#index)