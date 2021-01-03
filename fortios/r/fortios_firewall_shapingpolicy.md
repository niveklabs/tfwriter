# fortios_firewall_shapingpolicy

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
module "fortios_firewall_shapingpolicy" {
  source = "./modules/fortios/r/fortios_firewall_shapingpolicy"

  # class_id - (optional) is a type of number
  class_id = null
  # comment - (optional) is a type of string
  comment = null
  # diffserv_forward - (optional) is a type of string
  diffserv_forward = null
  # diffserv_reverse - (optional) is a type of string
  diffserv_reverse = null
  # diffservcode_forward - (optional) is a type of string
  diffservcode_forward = null
  # diffservcode_rev - (optional) is a type of string
  diffservcode_rev = null
  # fosid - (optional) is a type of number
  fosid = null
  # internet_service - (optional) is a type of string
  internet_service = null
  # internet_service_src - (optional) is a type of string
  internet_service_src = null
  # ip_version - (optional) is a type of string
  ip_version = null
  # name - (optional) is a type of string
  name = null
  # per_ip_shaper - (optional) is a type of string
  per_ip_shaper = null
  # schedule - (optional) is a type of string
  schedule = null
  # status - (optional) is a type of string
  status = null
  # tos - (optional) is a type of string
  tos = null
  # tos_mask - (optional) is a type of string
  tos_mask = null
  # tos_negate - (optional) is a type of string
  tos_negate = null
  # traffic_shaper - (optional) is a type of string
  traffic_shaper = null
  # traffic_shaper_reverse - (optional) is a type of string
  traffic_shaper_reverse = null

  app_category = [{
    id = null
  }]

  app_group = [{
    name = null
  }]

  application = [{
    id = null
  }]

  dstaddr = [{
    name = null
  }]

  dstaddr6 = [{
    name = null
  }]

  dstintf = [{
    name = null
  }]

  groups = [{
    name = null
  }]

  internet_service_custom = [{
    name = null
  }]

  internet_service_custom_group = [{
    name = null
  }]

  internet_service_group = [{
    name = null
  }]

  internet_service_id = [{
    id = null
  }]

  internet_service_src_custom = [{
    name = null
  }]

  internet_service_src_custom_group = [{
    name = null
  }]

  internet_service_src_group = [{
    name = null
  }]

  internet_service_src_id = [{
    id = null
  }]

  service = [{
    name = null
  }]

  srcaddr = [{
    name = null
  }]

  srcaddr6 = [{
    name = null
  }]

  url_category = [{
    id = null
  }]

  users = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "class_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffserv_forward" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffserv_reverse" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffservcode_forward" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "diffservcode_rev" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "internet_service" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_service_src" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "per_ip_shaper" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tos" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tos_mask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tos_negate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_shaper" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_shaper_reverse" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "app_category" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "app_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "application" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "dstaddr" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "dstaddr6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "dstintf" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "groups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_custom" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_custom_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_id" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "internet_service_src_custom" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_src_custom_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_src_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_src_id" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "service" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "srcaddr" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "srcaddr6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "url_category" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}

variable "users" {
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
resource "fortios_firewall_shapingpolicy" "this" {
  class_id               = var.class_id
  comment                = var.comment
  diffserv_forward       = var.diffserv_forward
  diffserv_reverse       = var.diffserv_reverse
  diffservcode_forward   = var.diffservcode_forward
  diffservcode_rev       = var.diffservcode_rev
  fosid                  = var.fosid
  internet_service       = var.internet_service
  internet_service_src   = var.internet_service_src
  ip_version             = var.ip_version
  name                   = var.name
  per_ip_shaper          = var.per_ip_shaper
  schedule               = var.schedule
  status                 = var.status
  tos                    = var.tos
  tos_mask               = var.tos_mask
  tos_negate             = var.tos_negate
  traffic_shaper         = var.traffic_shaper
  traffic_shaper_reverse = var.traffic_shaper_reverse

  dynamic "app_category" {
    for_each = var.app_category
    content {
      id = app_category.value["id"]
    }
  }

  dynamic "app_group" {
    for_each = var.app_group
    content {
      name = app_group.value["name"]
    }
  }

  dynamic "application" {
    for_each = var.application
    content {
      id = application.value["id"]
    }
  }

  dynamic "dstaddr" {
    for_each = var.dstaddr
    content {
      name = dstaddr.value["name"]
    }
  }

  dynamic "dstaddr6" {
    for_each = var.dstaddr6
    content {
      name = dstaddr6.value["name"]
    }
  }

  dynamic "dstintf" {
    for_each = var.dstintf
    content {
      name = dstintf.value["name"]
    }
  }

  dynamic "groups" {
    for_each = var.groups
    content {
      name = groups.value["name"]
    }
  }

  dynamic "internet_service_custom" {
    for_each = var.internet_service_custom
    content {
      name = internet_service_custom.value["name"]
    }
  }

  dynamic "internet_service_custom_group" {
    for_each = var.internet_service_custom_group
    content {
      name = internet_service_custom_group.value["name"]
    }
  }

  dynamic "internet_service_group" {
    for_each = var.internet_service_group
    content {
      name = internet_service_group.value["name"]
    }
  }

  dynamic "internet_service_id" {
    for_each = var.internet_service_id
    content {
      id = internet_service_id.value["id"]
    }
  }

  dynamic "internet_service_src_custom" {
    for_each = var.internet_service_src_custom
    content {
      name = internet_service_src_custom.value["name"]
    }
  }

  dynamic "internet_service_src_custom_group" {
    for_each = var.internet_service_src_custom_group
    content {
      name = internet_service_src_custom_group.value["name"]
    }
  }

  dynamic "internet_service_src_group" {
    for_each = var.internet_service_src_group
    content {
      name = internet_service_src_group.value["name"]
    }
  }

  dynamic "internet_service_src_id" {
    for_each = var.internet_service_src_id
    content {
      id = internet_service_src_id.value["id"]
    }
  }

  dynamic "service" {
    for_each = var.service
    content {
      name = service.value["name"]
    }
  }

  dynamic "srcaddr" {
    for_each = var.srcaddr
    content {
      name = srcaddr.value["name"]
    }
  }

  dynamic "srcaddr6" {
    for_each = var.srcaddr6
    content {
      name = srcaddr6.value["name"]
    }
  }

  dynamic "url_category" {
    for_each = var.url_category
    content {
      id = url_category.value["id"]
    }
  }

  dynamic "users" {
    for_each = var.users
    content {
      name = users.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "class_id" {
  description = "returns a number"
  value       = fortios_firewall_shapingpolicy.this.class_id
}

output "diffserv_forward" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.diffserv_forward
}

output "diffserv_reverse" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.diffserv_reverse
}

output "diffservcode_forward" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.diffservcode_forward
}

output "diffservcode_rev" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.diffservcode_rev
}

output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_shapingpolicy.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.id
}

output "internet_service" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.internet_service
}

output "internet_service_src" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.internet_service_src
}

output "ip_version" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.ip_version
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.name
}

output "per_ip_shaper" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.per_ip_shaper
}

output "schedule" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.schedule
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.status
}

output "tos" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.tos
}

output "tos_mask" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.tos_mask
}

output "tos_negate" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.tos_negate
}

output "traffic_shaper" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.traffic_shaper
}

output "traffic_shaper_reverse" {
  description = "returns a string"
  value       = fortios_firewall_shapingpolicy.this.traffic_shaper_reverse
}

output "this" {
  value = fortios_firewall_shapingpolicy.this
}
```

[top](#index)