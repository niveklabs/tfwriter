# fortios_firewall_address

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
module "fortios_firewall_address" {
  source = "./modules/fortios/r/fortios_firewall_address"

  # allow_routing - (optional) is a type of string
  allow_routing = null
  # associated_interface - (optional) is a type of string
  associated_interface = null
  # cache_ttl - (optional) is a type of number
  cache_ttl = null
  # clearpass_spt - (optional) is a type of string
  clearpass_spt = null
  # color - (optional) is a type of number
  color = null
  # comment - (optional) is a type of string
  comment = null
  # country - (optional) is a type of string
  country = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # end_ip - (optional) is a type of string
  end_ip = null
  # end_mac - (optional) is a type of string
  end_mac = null
  # epg_name - (optional) is a type of string
  epg_name = null
  # filter - (optional) is a type of string
  filter = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # interface - (optional) is a type of string
  interface = null
  # name - (optional) is a type of string
  name = null
  # node_ip_only - (optional) is a type of string
  node_ip_only = null
  # obj_id - (optional) is a type of string
  obj_id = null
  # obj_tag - (optional) is a type of string
  obj_tag = null
  # obj_type - (optional) is a type of string
  obj_type = null
  # organization - (optional) is a type of string
  organization = null
  # policy_group - (optional) is a type of string
  policy_group = null
  # sdn - (optional) is a type of string
  sdn = null
  # sdn_addr_type - (optional) is a type of string
  sdn_addr_type = null
  # sdn_tag - (optional) is a type of string
  sdn_tag = null
  # start_ip - (optional) is a type of string
  start_ip = null
  # start_mac - (optional) is a type of string
  start_mac = null
  # sub_type - (optional) is a type of string
  sub_type = null
  # subnet - (optional) is a type of string
  subnet = null
  # subnet_name - (optional) is a type of string
  subnet_name = null
  # tenant - (optional) is a type of string
  tenant = null
  # type - (optional) is a type of string
  type = null
  # uuid - (optional) is a type of string
  uuid = null
  # visibility - (optional) is a type of string
  visibility = null
  # wildcard - (optional) is a type of string
  wildcard = null
  # wildcard_fqdn - (optional) is a type of string
  wildcard_fqdn = null

  fsso_group = [{
    name = null
  }]

  list = [{
    ip = null
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
variable "allow_routing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "associated_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cache_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "clearpass_spt" {
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

variable "country" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "epg_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "node_ip_only" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "obj_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "obj_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "obj_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "organization" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sdn_addr_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sdn_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sub_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
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

variable "wildcard" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wildcard_fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fsso_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip = string
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
resource "fortios_firewall_address" "this" {
  # allow_routing - (optional) is a type of string
  allow_routing = var.allow_routing
  # associated_interface - (optional) is a type of string
  associated_interface = var.associated_interface
  # cache_ttl - (optional) is a type of number
  cache_ttl = var.cache_ttl
  # clearpass_spt - (optional) is a type of string
  clearpass_spt = var.clearpass_spt
  # color - (optional) is a type of number
  color = var.color
  # comment - (optional) is a type of string
  comment = var.comment
  # country - (optional) is a type of string
  country = var.country
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # end_ip - (optional) is a type of string
  end_ip = var.end_ip
  # end_mac - (optional) is a type of string
  end_mac = var.end_mac
  # epg_name - (optional) is a type of string
  epg_name = var.epg_name
  # filter - (optional) is a type of string
  filter = var.filter
  # fqdn - (optional) is a type of string
  fqdn = var.fqdn
  # interface - (optional) is a type of string
  interface = var.interface
  # name - (optional) is a type of string
  name = var.name
  # node_ip_only - (optional) is a type of string
  node_ip_only = var.node_ip_only
  # obj_id - (optional) is a type of string
  obj_id = var.obj_id
  # obj_tag - (optional) is a type of string
  obj_tag = var.obj_tag
  # obj_type - (optional) is a type of string
  obj_type = var.obj_type
  # organization - (optional) is a type of string
  organization = var.organization
  # policy_group - (optional) is a type of string
  policy_group = var.policy_group
  # sdn - (optional) is a type of string
  sdn = var.sdn
  # sdn_addr_type - (optional) is a type of string
  sdn_addr_type = var.sdn_addr_type
  # sdn_tag - (optional) is a type of string
  sdn_tag = var.sdn_tag
  # start_ip - (optional) is a type of string
  start_ip = var.start_ip
  # start_mac - (optional) is a type of string
  start_mac = var.start_mac
  # sub_type - (optional) is a type of string
  sub_type = var.sub_type
  # subnet - (optional) is a type of string
  subnet = var.subnet
  # subnet_name - (optional) is a type of string
  subnet_name = var.subnet_name
  # tenant - (optional) is a type of string
  tenant = var.tenant
  # type - (optional) is a type of string
  type = var.type
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # visibility - (optional) is a type of string
  visibility = var.visibility
  # wildcard - (optional) is a type of string
  wildcard = var.wildcard
  # wildcard_fqdn - (optional) is a type of string
  wildcard_fqdn = var.wildcard_fqdn

  dynamic "fsso_group" {
    for_each = var.fsso_group
    content {
      # name - (optional) is a type of string
      name = fsso_group.value["name"]
    }
  }

  dynamic "list" {
    for_each = var.list
    content {
      # ip - (optional) is a type of string
      ip = list.value["ip"]
    }
  }

  dynamic "tagging" {
    for_each = var.tagging
    content {
      # category - (optional) is a type of string
      category = tagging.value["category"]
      # name - (optional) is a type of string
      name = tagging.value["name"]

      dynamic "tags" {
        for_each = tagging.value.tags
        content {
          # name - (optional) is a type of string
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
output "allow_routing" {
  description = "returns a string"
  value       = fortios_firewall_address.this.allow_routing
}

output "associated_interface" {
  description = "returns a string"
  value       = fortios_firewall_address.this.associated_interface
}

output "cache_ttl" {
  description = "returns a number"
  value       = fortios_firewall_address.this.cache_ttl
}

output "clearpass_spt" {
  description = "returns a string"
  value       = fortios_firewall_address.this.clearpass_spt
}

output "color" {
  description = "returns a number"
  value       = fortios_firewall_address.this.color
}

output "country" {
  description = "returns a string"
  value       = fortios_firewall_address.this.country
}

output "end_ip" {
  description = "returns a string"
  value       = fortios_firewall_address.this.end_ip
}

output "end_mac" {
  description = "returns a string"
  value       = fortios_firewall_address.this.end_mac
}

output "epg_name" {
  description = "returns a string"
  value       = fortios_firewall_address.this.epg_name
}

output "fqdn" {
  description = "returns a string"
  value       = fortios_firewall_address.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_address.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_firewall_address.this.interface
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_address.this.name
}

output "node_ip_only" {
  description = "returns a string"
  value       = fortios_firewall_address.this.node_ip_only
}

output "obj_tag" {
  description = "returns a string"
  value       = fortios_firewall_address.this.obj_tag
}

output "obj_type" {
  description = "returns a string"
  value       = fortios_firewall_address.this.obj_type
}

output "organization" {
  description = "returns a string"
  value       = fortios_firewall_address.this.organization
}

output "policy_group" {
  description = "returns a string"
  value       = fortios_firewall_address.this.policy_group
}

output "sdn" {
  description = "returns a string"
  value       = fortios_firewall_address.this.sdn
}

output "sdn_addr_type" {
  description = "returns a string"
  value       = fortios_firewall_address.this.sdn_addr_type
}

output "sdn_tag" {
  description = "returns a string"
  value       = fortios_firewall_address.this.sdn_tag
}

output "start_ip" {
  description = "returns a string"
  value       = fortios_firewall_address.this.start_ip
}

output "start_mac" {
  description = "returns a string"
  value       = fortios_firewall_address.this.start_mac
}

output "sub_type" {
  description = "returns a string"
  value       = fortios_firewall_address.this.sub_type
}

output "subnet" {
  description = "returns a string"
  value       = fortios_firewall_address.this.subnet
}

output "subnet_name" {
  description = "returns a string"
  value       = fortios_firewall_address.this.subnet_name
}

output "tenant" {
  description = "returns a string"
  value       = fortios_firewall_address.this.tenant
}

output "type" {
  description = "returns a string"
  value       = fortios_firewall_address.this.type
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_address.this.uuid
}

output "visibility" {
  description = "returns a string"
  value       = fortios_firewall_address.this.visibility
}

output "wildcard" {
  description = "returns a string"
  value       = fortios_firewall_address.this.wildcard
}

output "wildcard_fqdn" {
  description = "returns a string"
  value       = fortios_firewall_address.this.wildcard_fqdn
}

output "this" {
  value = fortios_firewall_address.this
}
```

[top](#index)