# alicloud_fc_custom_domain

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
module "alicloud_fc_custom_domain" {
  source = "./modules/alicloud/r/alicloud_fc_custom_domain"

  # domain_name - (required) is a type of string
  domain_name = null
  # protocol - (required) is a type of string
  protocol = null

  cert_config = [{
    cert_name   = null
    certificate = null
    private_key = null
  }]

  route_config = [{
    function_name = null
    methods       = []
    path          = null
    qualifier     = null
    service_name  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "cert_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cert_name   = string
      certificate = string
      private_key = string
    }
  ))
  default = []
}

variable "route_config" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      function_name = string
      methods       = list(string)
      path          = string
      qualifier     = string
      service_name  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_fc_custom_domain" "this" {
  # domain_name - (required) is a type of string
  domain_name = var.domain_name
  # protocol - (required) is a type of string
  protocol = var.protocol

  dynamic "cert_config" {
    for_each = var.cert_config
    content {
      # cert_name - (required) is a type of string
      cert_name = cert_config.value["cert_name"]
      # certificate - (required) is a type of string
      certificate = cert_config.value["certificate"]
      # private_key - (required) is a type of string
      private_key = cert_config.value["private_key"]
    }
  }

  dynamic "route_config" {
    for_each = var.route_config
    content {
      # function_name - (required) is a type of string
      function_name = route_config.value["function_name"]
      # methods - (optional) is a type of list of string
      methods = route_config.value["methods"]
      # path - (required) is a type of string
      path = route_config.value["path"]
      # qualifier - (optional) is a type of string
      qualifier = route_config.value["qualifier"]
      # service_name - (required) is a type of string
      service_name = route_config.value["service_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = alicloud_fc_custom_domain.this.account_id
}

output "api_version" {
  description = "returns a string"
  value       = alicloud_fc_custom_domain.this.api_version
}

output "created_time" {
  description = "returns a string"
  value       = alicloud_fc_custom_domain.this.created_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_fc_custom_domain.this.id
}

output "last_modified_time" {
  description = "returns a string"
  value       = alicloud_fc_custom_domain.this.last_modified_time
}

output "this" {
  value = alicloud_fc_custom_domain.this
}
```

[top](#index)