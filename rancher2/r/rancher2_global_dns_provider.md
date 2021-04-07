# rancher2_global_dns_provider

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_global_dns_provider" {
  source = "./modules/rancher2/r/rancher2_global_dns_provider"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # root_domain - (required) is a type of string
  root_domain = null

  alidns_config = [{
    access_key = null
    secret_key = null
  }]

  cloudflare_config = [{
    api_email     = null
    api_key       = null
    proxy_setting = null
  }]

  route53_config = [{
    access_key       = null
    credentials_path = null
    region           = null
    role_arn         = null
    secret_key       = null
    zone_type        = null
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
variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "root_domain" {
  description = "(required)"
  type        = string
}

variable "alidns_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_key = string
      secret_key = string
    }
  ))
  default = []
}

variable "cloudflare_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      api_email     = string
      api_key       = string
      proxy_setting = bool
    }
  ))
  default = []
}

variable "route53_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_key       = string
      credentials_path = string
      region           = string
      role_arn         = string
      secret_key       = string
      zone_type        = string
    }
  ))
  default = []
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
resource "rancher2_global_dns_provider" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # root_domain - (required) is a type of string
  root_domain = var.root_domain

  dynamic "alidns_config" {
    for_each = var.alidns_config
    content {
      # access_key - (required) is a type of string
      access_key = alidns_config.value["access_key"]
      # secret_key - (required) is a type of string
      secret_key = alidns_config.value["secret_key"]
    }
  }

  dynamic "cloudflare_config" {
    for_each = var.cloudflare_config
    content {
      # api_email - (required) is a type of string
      api_email = cloudflare_config.value["api_email"]
      # api_key - (required) is a type of string
      api_key = cloudflare_config.value["api_key"]
      # proxy_setting - (optional) is a type of bool
      proxy_setting = cloudflare_config.value["proxy_setting"]
    }
  }

  dynamic "route53_config" {
    for_each = var.route53_config
    content {
      # access_key - (required) is a type of string
      access_key = route53_config.value["access_key"]
      # credentials_path - (optional) is a type of string
      credentials_path = route53_config.value["credentials_path"]
      # region - (optional) is a type of string
      region = route53_config.value["region"]
      # role_arn - (optional) is a type of string
      role_arn = route53_config.value["role_arn"]
      # secret_key - (required) is a type of string
      secret_key = route53_config.value["secret_key"]
      # zone_type - (optional) is a type of string
      zone_type = route53_config.value["zone_type"]
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
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_global_dns_provider.this.annotations
}

output "dns_provider" {
  description = "returns a string"
  value       = rancher2_global_dns_provider.this.dns_provider
}

output "id" {
  description = "returns a string"
  value       = rancher2_global_dns_provider.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_global_dns_provider.this.labels
}

output "this" {
  value = rancher2_global_dns_provider.this
}
```

[top](#index)