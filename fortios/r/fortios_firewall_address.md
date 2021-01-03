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
    fortios = ">= 1.6.18"
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
  # color - (optional) is a type of number
  color = null
  # comment - (optional) is a type of string
  comment = null
  # country - (optional) is a type of string
  country = null
  # end_ip - (optional) is a type of string
  end_ip = null
  # epg_name - (optional) is a type of string
  epg_name = null
  # filter - (optional) is a type of string
  filter = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # name - (optional) is a type of string
  name = null
  # obj_id - (optional) is a type of string
  obj_id = null
  # organization - (optional) is a type of string
  organization = null
  # policy_group - (optional) is a type of string
  policy_group = null
  # sdn - (optional) is a type of string
  sdn = null
  # sdn_tag - (optional) is a type of string
  sdn_tag = null
  # start_ip - (optional) is a type of string
  start_ip = null
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

variable "end_ip" {
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "obj_id" {
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
  allow_routing        = var.allow_routing
  associated_interface = var.associated_interface
  cache_ttl            = var.cache_ttl
  color                = var.color
  comment              = var.comment
  country              = var.country
  end_ip               = var.end_ip
  epg_name             = var.epg_name
  filter               = var.filter
  fqdn                 = var.fqdn
  name                 = var.name
  obj_id               = var.obj_id
  organization         = var.organization
  policy_group         = var.policy_group
  sdn                  = var.sdn
  sdn_tag              = var.sdn_tag
  start_ip             = var.start_ip
  subnet               = var.subnet
  subnet_name          = var.subnet_name
  tenant               = var.tenant
  type                 = var.type
  uuid                 = var.uuid
  visibility           = var.visibility
  wildcard             = var.wildcard
  wildcard_fqdn        = var.wildcard_fqdn

  dynamic "list" {
    for_each = var.list
    content {
      ip = list.value["ip"]
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

output "name" {
  description = "returns a string"
  value       = fortios_firewall_address.this.name
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

output "sdn_tag" {
  description = "returns a string"
  value       = fortios_firewall_address.this.sdn_tag
}

output "start_ip" {
  description = "returns a string"
  value       = fortios_firewall_address.this.start_ip
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