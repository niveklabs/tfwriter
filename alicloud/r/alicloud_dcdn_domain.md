# alicloud_dcdn_domain

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_dcdn_domain" {
  source = "./modules/alicloud/r/alicloud_dcdn_domain"

  # cert_name - (optional) is a type of string
  cert_name = null
  # cert_type - (optional) is a type of string
  cert_type = null
  # check_url - (optional) is a type of string
  check_url = null
  # domain_name - (required) is a type of string
  domain_name = null
  # force_set - (optional) is a type of string
  force_set = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # scope - (optional) is a type of string
  scope = null
  # security_token - (optional) is a type of string
  security_token = null
  # ssl_pri - (optional) is a type of string
  ssl_pri = null
  # ssl_protocol - (optional) is a type of string
  ssl_protocol = null
  # ssl_pub - (optional) is a type of string
  ssl_pub = null
  # status - (optional) is a type of string
  status = null
  # top_level_domain - (optional) is a type of string
  top_level_domain = null

  sources = [{
    content  = null
    port     = null
    priority = null
    type     = null
    weight   = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cert_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cert_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "check_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "force_set" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_pri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_pub" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "top_level_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sources" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      content  = string
      port     = number
      priority = string
      type     = string
      weight   = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_dcdn_domain" "this" {
  # cert_name - (optional) is a type of string
  cert_name = var.cert_name
  # cert_type - (optional) is a type of string
  cert_type = var.cert_type
  # check_url - (optional) is a type of string
  check_url = var.check_url
  # domain_name - (required) is a type of string
  domain_name = var.domain_name
  # force_set - (optional) is a type of string
  force_set = var.force_set
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # scope - (optional) is a type of string
  scope = var.scope
  # security_token - (optional) is a type of string
  security_token = var.security_token
  # ssl_pri - (optional) is a type of string
  ssl_pri = var.ssl_pri
  # ssl_protocol - (optional) is a type of string
  ssl_protocol = var.ssl_protocol
  # ssl_pub - (optional) is a type of string
  ssl_pub = var.ssl_pub
  # status - (optional) is a type of string
  status = var.status
  # top_level_domain - (optional) is a type of string
  top_level_domain = var.top_level_domain

  dynamic "sources" {
    for_each = var.sources
    content {
      # content - (required) is a type of string
      content = sources.value["content"]
      # port - (optional) is a type of number
      port = sources.value["port"]
      # priority - (optional) is a type of string
      priority = sources.value["priority"]
      # type - (required) is a type of string
      type = sources.value["type"]
      # weight - (optional) is a type of string
      weight = sources.value["weight"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cert_name" {
  description = "returns a string"
  value       = alicloud_dcdn_domain.this.cert_name
}

output "id" {
  description = "returns a string"
  value       = alicloud_dcdn_domain.this.id
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_dcdn_domain.this.resource_group_id
}

output "this" {
  value = alicloud_dcdn_domain.this
}
```

[top](#index)