# fortios_webproxy_profile

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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_webproxy_profile" {
  source = "./modules/fortios/r/fortios_webproxy_profile"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # header_client_ip - (optional) is a type of string
  header_client_ip = null
  # header_front_end_https - (optional) is a type of string
  header_front_end_https = null
  # header_via_request - (optional) is a type of string
  header_via_request = null
  # header_via_response - (optional) is a type of string
  header_via_response = null
  # header_x_authenticated_groups - (optional) is a type of string
  header_x_authenticated_groups = null
  # header_x_authenticated_user - (optional) is a type of string
  header_x_authenticated_user = null
  # header_x_forwarded_for - (optional) is a type of string
  header_x_forwarded_for = null
  # log_header_change - (optional) is a type of string
  log_header_change = null
  # name - (optional) is a type of string
  name = null
  # strip_encoding - (optional) is a type of string
  strip_encoding = null

  headers = [{
    action          = null
    add_option      = null
    base64_encoding = null
    content         = null
    dstaddr = [{
      name = null
    }]
    dstaddr6 = [{
      name = null
    }]
    id       = null
    name     = null
    protocol = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "header_client_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "header_front_end_https" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "header_via_request" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "header_via_response" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "header_x_authenticated_groups" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "header_x_authenticated_user" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "header_x_forwarded_for" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_header_change" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "strip_encoding" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "headers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action          = string
      add_option      = string
      base64_encoding = string
      content         = string
      dstaddr = list(object(
        {
          name = string
        }
      ))
      dstaddr6 = list(object(
        {
          name = string
        }
      ))
      id       = number
      name     = string
      protocol = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webproxy_profile" "this" {
  dynamic_sort_subtable         = var.dynamic_sort_subtable
  header_client_ip              = var.header_client_ip
  header_front_end_https        = var.header_front_end_https
  header_via_request            = var.header_via_request
  header_via_response           = var.header_via_response
  header_x_authenticated_groups = var.header_x_authenticated_groups
  header_x_authenticated_user   = var.header_x_authenticated_user
  header_x_forwarded_for        = var.header_x_forwarded_for
  log_header_change             = var.log_header_change
  name                          = var.name
  strip_encoding                = var.strip_encoding

  dynamic "headers" {
    for_each = var.headers
    content {
      action          = headers.value["action"]
      add_option      = headers.value["add_option"]
      base64_encoding = headers.value["base64_encoding"]
      content         = headers.value["content"]
      id              = headers.value["id"]
      name            = headers.value["name"]
      protocol        = headers.value["protocol"]

      dynamic "dstaddr" {
        for_each = headers.value.dstaddr
        content {
          name = dstaddr.value["name"]
        }
      }

      dynamic "dstaddr6" {
        for_each = headers.value.dstaddr6
        content {
          name = dstaddr6.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "header_client_ip" {
  description = "returns a string"
  value       = fortios_webproxy_profile.this.header_client_ip
}

output "header_front_end_https" {
  description = "returns a string"
  value       = fortios_webproxy_profile.this.header_front_end_https
}

output "header_via_request" {
  description = "returns a string"
  value       = fortios_webproxy_profile.this.header_via_request
}

output "header_via_response" {
  description = "returns a string"
  value       = fortios_webproxy_profile.this.header_via_response
}

output "header_x_authenticated_groups" {
  description = "returns a string"
  value       = fortios_webproxy_profile.this.header_x_authenticated_groups
}

output "header_x_authenticated_user" {
  description = "returns a string"
  value       = fortios_webproxy_profile.this.header_x_authenticated_user
}

output "header_x_forwarded_for" {
  description = "returns a string"
  value       = fortios_webproxy_profile.this.header_x_forwarded_for
}

output "id" {
  description = "returns a string"
  value       = fortios_webproxy_profile.this.id
}

output "log_header_change" {
  description = "returns a string"
  value       = fortios_webproxy_profile.this.log_header_change
}

output "name" {
  description = "returns a string"
  value       = fortios_webproxy_profile.this.name
}

output "strip_encoding" {
  description = "returns a string"
  value       = fortios_webproxy_profile.this.strip_encoding
}

output "this" {
  value = fortios_webproxy_profile.this
}
```

[top](#index)