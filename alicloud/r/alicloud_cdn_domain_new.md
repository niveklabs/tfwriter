# alicloud_cdn_domain_new

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
module "alicloud_cdn_domain_new" {
  source = "./modules/alicloud/r/alicloud_cdn_domain_new"

  # cdn_type - (required) is a type of string
  cdn_type = null
  # domain_name - (required) is a type of string
  domain_name = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # scope - (optional) is a type of string
  scope = null
  # tags - (optional) is a type of map of string
  tags = {}

  certificate_config = [{
    cert_name                 = null
    cert_type                 = null
    force_set                 = null
    private_key               = null
    server_certificate        = null
    server_certificate_status = null
  }]

  sources = [{
    content  = null
    port     = null
    priority = null
    type     = null
    weight   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cdn_type" {
  description = "(required)"
  type        = string
}

variable "domain_name" {
  description = "(required)"
  type        = string
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "certificate_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cert_name                 = string
      cert_type                 = string
      force_set                 = string
      private_key               = string
      server_certificate        = string
      server_certificate_status = string
    }
  ))
  default = []
}

variable "sources" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      content  = string
      port     = number
      priority = number
      type     = string
      weight   = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cdn_domain_new" "this" {
  cdn_type          = var.cdn_type
  domain_name       = var.domain_name
  resource_group_id = var.resource_group_id
  scope             = var.scope
  tags              = var.tags

  dynamic "certificate_config" {
    for_each = var.certificate_config
    content {
      cert_name                 = certificate_config.value["cert_name"]
      cert_type                 = certificate_config.value["cert_type"]
      force_set                 = certificate_config.value["force_set"]
      private_key               = certificate_config.value["private_key"]
      server_certificate        = certificate_config.value["server_certificate"]
      server_certificate_status = certificate_config.value["server_certificate_status"]
    }
  }

  dynamic "sources" {
    for_each = var.sources
    content {
      content  = sources.value["content"]
      port     = sources.value["port"]
      priority = sources.value["priority"]
      type     = sources.value["type"]
      weight   = sources.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cname" {
  description = "returns a string"
  value       = alicloud_cdn_domain_new.this.cname
}

output "id" {
  description = "returns a string"
  value       = alicloud_cdn_domain_new.this.id
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_cdn_domain_new.this.resource_group_id
}

output "scope" {
  description = "returns a string"
  value       = alicloud_cdn_domain_new.this.scope
}

output "this" {
  value = alicloud_cdn_domain_new.this
}
```

[top](#index)