# thunder_slb_template_logging

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
module "thunder_slb_template_logging" {
  source = "./modules/thunder/r/thunder_slb_template_logging"

  # auto - (optional) is a type of string
  auto = null
  # format - (optional) is a type of string
  format = null
  # keep_end - (optional) is a type of number
  keep_end = null
  # keep_start - (optional) is a type of number
  keep_start = null
  # local_logging - (optional) is a type of number
  local_logging = null
  # mask - (optional) is a type of string
  mask = null
  # name - (optional) is a type of string
  name = null
  # pcre_mask - (optional) is a type of string
  pcre_mask = null
  # pool - (optional) is a type of string
  pool = null
  # pool_shared - (optional) is a type of string
  pool_shared = null
  # service_group - (optional) is a type of string
  service_group = null
  # shared_partition_pool - (optional) is a type of number
  shared_partition_pool = null
  # shared_partition_tcp_proxy_template - (optional) is a type of number
  shared_partition_tcp_proxy_template = null
  # tcp_proxy - (optional) is a type of string
  tcp_proxy = null
  # template_tcp_proxy_shared - (optional) is a type of string
  template_tcp_proxy_shared = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "auto" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "keep_end" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "keep_start" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "local_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pcre_mask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pool" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pool_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shared_partition_pool" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_partition_tcp_proxy_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tcp_proxy" {
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
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_logging" "this" {
  auto                                = var.auto
  format                              = var.format
  keep_end                            = var.keep_end
  keep_start                          = var.keep_start
  local_logging                       = var.local_logging
  mask                                = var.mask
  name                                = var.name
  pcre_mask                           = var.pcre_mask
  pool                                = var.pool
  pool_shared                         = var.pool_shared
  service_group                       = var.service_group
  shared_partition_pool               = var.shared_partition_pool
  shared_partition_tcp_proxy_template = var.shared_partition_tcp_proxy_template
  tcp_proxy                           = var.tcp_proxy
  template_tcp_proxy_shared           = var.template_tcp_proxy_shared
  user_tag                            = var.user_tag
  uuid                                = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_logging.this.id
}

output "this" {
  value = thunder_slb_template_logging.this
}
```

[top](#index)