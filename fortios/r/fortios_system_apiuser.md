# fortios_system_apiuser

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
module "fortios_system_apiuser" {
  source = "./modules/fortios/r/fortios_system_apiuser"

  # accprofile - (required) is a type of string
  accprofile = null
  # api_key - (optional) is a type of string
  api_key = null
  # comments - (optional) is a type of string
  comments = null
  # cors_allow_origin - (optional) is a type of string
  cors_allow_origin = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null
  # peer_auth - (optional) is a type of string
  peer_auth = null
  # peer_group - (optional) is a type of string
  peer_group = null
  # schedule - (optional) is a type of string
  schedule = null

  trusthost = [{
    id             = null
    ipv4_trusthost = null
    ipv6_trusthost = null
    type           = null
  }]

  vdom = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accprofile" {
  description = "(required)"
  type        = string
}

variable "api_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cors_allow_origin" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id             = number
      ipv4_trusthost = string
      ipv6_trusthost = string
      type           = string
    }
  ))
  default = []
}

variable "vdom" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_apiuser" "this" {
  # accprofile - (required) is a type of string
  accprofile = var.accprofile
  # api_key - (optional) is a type of string
  api_key = var.api_key
  # comments - (optional) is a type of string
  comments = var.comments
  # cors_allow_origin - (optional) is a type of string
  cors_allow_origin = var.cors_allow_origin
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name
  # peer_auth - (optional) is a type of string
  peer_auth = var.peer_auth
  # peer_group - (optional) is a type of string
  peer_group = var.peer_group
  # schedule - (optional) is a type of string
  schedule = var.schedule

  dynamic "trusthost" {
    for_each = var.trusthost
    content {
      # id - (optional) is a type of number
      id = trusthost.value["id"]
      # ipv4_trusthost - (optional) is a type of string
      ipv4_trusthost = trusthost.value["ipv4_trusthost"]
      # ipv6_trusthost - (optional) is a type of string
      ipv6_trusthost = trusthost.value["ipv6_trusthost"]
      # type - (optional) is a type of string
      type = trusthost.value["type"]
    }
  }

  dynamic "vdom" {
    for_each = var.vdom
    content {
      # name - (optional) is a type of string
      name = vdom.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cors_allow_origin" {
  description = "returns a string"
  value       = fortios_system_apiuser.this.cors_allow_origin
}

output "id" {
  description = "returns a string"
  value       = fortios_system_apiuser.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_apiuser.this.name
}

output "peer_auth" {
  description = "returns a string"
  value       = fortios_system_apiuser.this.peer_auth
}

output "peer_group" {
  description = "returns a string"
  value       = fortios_system_apiuser.this.peer_group
}

output "schedule" {
  description = "returns a string"
  value       = fortios_system_apiuser.this.schedule
}

output "this" {
  value = fortios_system_apiuser.this
}
```

[top](#index)