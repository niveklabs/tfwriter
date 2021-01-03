# fortios_firewall_proxyaddress

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_firewall_proxyaddress" {
  source = "./modules/fortios/r/fortios_firewall_proxyaddress"

  # case_sensitivity - (optional) is a type of string
  case_sensitivity = null
  # color - (optional) is a type of number
  color = null
  # comment - (optional) is a type of string
  comment = null
  # header - (optional) is a type of string
  header = null
  # header_name - (optional) is a type of string
  header_name = null
  # host - (optional) is a type of string
  host = null
  # host_regex - (optional) is a type of string
  host_regex = null
  # method - (optional) is a type of string
  method = null
  # name - (optional) is a type of string
  name = null
  # path - (optional) is a type of string
  path = null
  # query - (optional) is a type of string
  query = null
  # referrer - (optional) is a type of string
  referrer = null
  # type - (optional) is a type of string
  type = null
  # ua - (optional) is a type of string
  ua = null
  # uuid - (optional) is a type of string
  uuid = null
  # visibility - (optional) is a type of string
  visibility = null

  category = [{
    id = null
  }]

  header_group = [{
    case_sensitivity = null
    header           = null
    header_name      = null
    id               = null
  }]

  tagging = [{
    category = null
    name     = null
    tags = [{
      name = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "case_sensitivity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "color" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "header" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "header_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "query" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "referrer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ua" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "visibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "category" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "header_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      case_sensitivity = string
      header           = string
      header_name      = string
      id               = number
    }
  ))
  default = []
}

variable "tagging" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      category = string
      name     = string
      tags = list(object(
        {
          name = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_proxyaddress" "this" {
  case_sensitivity = var.case_sensitivity
  color            = var.color
  comment          = var.comment
  header           = var.header
  header_name      = var.header_name
  host             = var.host
  host_regex       = var.host_regex
  method           = var.method
  name             = var.name
  path             = var.path
  query            = var.query
  referrer         = var.referrer
  type             = var.type
  ua               = var.ua
  uuid             = var.uuid
  visibility       = var.visibility

  dynamic "category" {
    for_each = var.category
    content {
      id = category.value["id"]
    }
  }

  dynamic "header_group" {
    for_each = var.header_group
    content {
      case_sensitivity = header_group.value["case_sensitivity"]
      header           = header_group.value["header"]
      header_name      = header_group.value["header_name"]
      id               = header_group.value["id"]
    }
  }

  dynamic "tagging" {
    for_each = var.tagging
    content {
      category = tagging.value["category"]
      name     = tagging.value["name"]

      dynamic "tags" {
        for_each = tagging.value.tags
        content {
          name = tags.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "case_sensitivity" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.case_sensitivity
}

output "color" {
  description = "returns a number"
  value       = fortios_firewall_proxyaddress.this.color
}

output "header" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.header
}

output "header_name" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.header_name
}

output "host" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.host
}

output "host_regex" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.host_regex
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.id
}

output "method" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.method
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.name
}

output "path" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.path
}

output "query" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.query
}

output "referrer" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.referrer
}

output "type" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.type
}

output "ua" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.ua
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.uuid
}

output "visibility" {
  description = "returns a string"
  value       = fortios_firewall_proxyaddress.this.visibility
}

output "this" {
  value = fortios_firewall_proxyaddress.this
}
```

[top](#index)