# alicloud_log_store_index

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
module "alicloud_log_store_index" {
  source = "./modules/alicloud/r/alicloud_log_store_index"

  # logstore - (required) is a type of string
  logstore = null
  # project - (required) is a type of string
  project = null

  field_search = [{
    alias            = null
    case_sensitive   = null
    enable_analytics = null
    include_chinese  = null
    json_keys = [{
      alias     = null
      doc_value = null
      name      = null
      type      = null
    }]
    name  = null
    token = null
    type  = null
  }]

  full_text = [{
    case_sensitive  = null
    include_chinese = null
    token           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "logstore" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "field_search" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      alias            = string
      case_sensitive   = bool
      enable_analytics = bool
      include_chinese  = bool
      json_keys = set(object(
        {
          alias     = string
          doc_value = bool
          name      = string
          type      = string
        }
      ))
      name  = string
      token = string
      type  = string
    }
  ))
  default = []
}

variable "full_text" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      case_sensitive  = bool
      include_chinese = bool
      token           = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_log_store_index" "this" {
  # logstore - (required) is a type of string
  logstore = var.logstore
  # project - (required) is a type of string
  project = var.project

  dynamic "field_search" {
    for_each = var.field_search
    content {
      # alias - (optional) is a type of string
      alias = field_search.value["alias"]
      # case_sensitive - (optional) is a type of bool
      case_sensitive = field_search.value["case_sensitive"]
      # enable_analytics - (optional) is a type of bool
      enable_analytics = field_search.value["enable_analytics"]
      # include_chinese - (optional) is a type of bool
      include_chinese = field_search.value["include_chinese"]
      # name - (required) is a type of string
      name = field_search.value["name"]
      # token - (optional) is a type of string
      token = field_search.value["token"]
      # type - (optional) is a type of string
      type = field_search.value["type"]

      dynamic "json_keys" {
        for_each = field_search.value.json_keys
        content {
          # alias - (optional) is a type of string
          alias = json_keys.value["alias"]
          # doc_value - (optional) is a type of bool
          doc_value = json_keys.value["doc_value"]
          # name - (required) is a type of string
          name = json_keys.value["name"]
          # type - (optional) is a type of string
          type = json_keys.value["type"]
        }
      }

    }
  }

  dynamic "full_text" {
    for_each = var.full_text
    content {
      # case_sensitive - (optional) is a type of bool
      case_sensitive = full_text.value["case_sensitive"]
      # include_chinese - (optional) is a type of bool
      include_chinese = full_text.value["include_chinese"]
      # token - (optional) is a type of string
      token = full_text.value["token"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_log_store_index.this.id
}

output "this" {
  value = alicloud_log_store_index.this
}
```

[top](#index)