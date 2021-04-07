# fortios_dnsfilter_profile

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
module "fortios_dnsfilter_profile" {
  source = "./modules/fortios/r/fortios_dnsfilter_profile"

  # block_action - (optional) is a type of string
  block_action = null
  # block_botnet - (optional) is a type of string
  block_botnet = null
  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # log_all_domain - (optional) is a type of string
  log_all_domain = null
  # name - (required) is a type of string
  name = null
  # redirect_portal - (optional) is a type of string
  redirect_portal = null
  # redirect_portal6 - (optional) is a type of string
  redirect_portal6 = null
  # safe_search - (optional) is a type of string
  safe_search = null
  # sdns_domain_log - (optional) is a type of string
  sdns_domain_log = null
  # sdns_ftgd_err_log - (optional) is a type of string
  sdns_ftgd_err_log = null
  # youtube_restrict - (optional) is a type of string
  youtube_restrict = null

  dns_translation = [{
    addr_type = null
    dst       = null
    dst6      = null
    id        = null
    netmask   = null
    prefix    = null
    src       = null
    src6      = null
    status    = null
  }]

  domain_filter = [{
    domain_filter_table = null
  }]

  external_ip_blocklist = [{
    name = null
  }]

  ftgd_dns = [{
    filters = [{
      action   = null
      category = null
      id       = null
      log      = null
    }]
    options = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "block_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "block_botnet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_all_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "redirect_portal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redirect_portal6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "safe_search" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sdns_domain_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sdns_ftgd_err_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "youtube_restrict" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_translation" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      addr_type = string
      dst       = string
      dst6      = string
      id        = number
      netmask   = string
      prefix    = number
      src       = string
      src6      = string
      status    = string
    }
  ))
  default = []
}

variable "domain_filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      domain_filter_table = number
    }
  ))
  default = []
}

variable "external_ip_blocklist" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "ftgd_dns" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      filters = list(object(
        {
          action   = string
          category = number
          id       = number
          log      = string
        }
      ))
      options = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_dnsfilter_profile" "this" {
  # block_action - (optional) is a type of string
  block_action = var.block_action
  # block_botnet - (optional) is a type of string
  block_botnet = var.block_botnet
  # comment - (optional) is a type of string
  comment = var.comment
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # log_all_domain - (optional) is a type of string
  log_all_domain = var.log_all_domain
  # name - (required) is a type of string
  name = var.name
  # redirect_portal - (optional) is a type of string
  redirect_portal = var.redirect_portal
  # redirect_portal6 - (optional) is a type of string
  redirect_portal6 = var.redirect_portal6
  # safe_search - (optional) is a type of string
  safe_search = var.safe_search
  # sdns_domain_log - (optional) is a type of string
  sdns_domain_log = var.sdns_domain_log
  # sdns_ftgd_err_log - (optional) is a type of string
  sdns_ftgd_err_log = var.sdns_ftgd_err_log
  # youtube_restrict - (optional) is a type of string
  youtube_restrict = var.youtube_restrict

  dynamic "dns_translation" {
    for_each = var.dns_translation
    content {
      # addr_type - (optional) is a type of string
      addr_type = dns_translation.value["addr_type"]
      # dst - (optional) is a type of string
      dst = dns_translation.value["dst"]
      # dst6 - (optional) is a type of string
      dst6 = dns_translation.value["dst6"]
      # id - (optional) is a type of number
      id = dns_translation.value["id"]
      # netmask - (optional) is a type of string
      netmask = dns_translation.value["netmask"]
      # prefix - (optional) is a type of number
      prefix = dns_translation.value["prefix"]
      # src - (optional) is a type of string
      src = dns_translation.value["src"]
      # src6 - (optional) is a type of string
      src6 = dns_translation.value["src6"]
      # status - (optional) is a type of string
      status = dns_translation.value["status"]
    }
  }

  dynamic "domain_filter" {
    for_each = var.domain_filter
    content {
      # domain_filter_table - (optional) is a type of number
      domain_filter_table = domain_filter.value["domain_filter_table"]
    }
  }

  dynamic "external_ip_blocklist" {
    for_each = var.external_ip_blocklist
    content {
      # name - (optional) is a type of string
      name = external_ip_blocklist.value["name"]
    }
  }

  dynamic "ftgd_dns" {
    for_each = var.ftgd_dns
    content {
      # options - (optional) is a type of string
      options = ftgd_dns.value["options"]

      dynamic "filters" {
        for_each = ftgd_dns.value.filters
        content {
          # action - (optional) is a type of string
          action = filters.value["action"]
          # category - (optional) is a type of number
          category = filters.value["category"]
          # id - (optional) is a type of number
          id = filters.value["id"]
          # log - (optional) is a type of string
          log = filters.value["log"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "block_action" {
  description = "returns a string"
  value       = fortios_dnsfilter_profile.this.block_action
}

output "block_botnet" {
  description = "returns a string"
  value       = fortios_dnsfilter_profile.this.block_botnet
}

output "id" {
  description = "returns a string"
  value       = fortios_dnsfilter_profile.this.id
}

output "log_all_domain" {
  description = "returns a string"
  value       = fortios_dnsfilter_profile.this.log_all_domain
}

output "redirect_portal" {
  description = "returns a string"
  value       = fortios_dnsfilter_profile.this.redirect_portal
}

output "redirect_portal6" {
  description = "returns a string"
  value       = fortios_dnsfilter_profile.this.redirect_portal6
}

output "safe_search" {
  description = "returns a string"
  value       = fortios_dnsfilter_profile.this.safe_search
}

output "sdns_domain_log" {
  description = "returns a string"
  value       = fortios_dnsfilter_profile.this.sdns_domain_log
}

output "sdns_ftgd_err_log" {
  description = "returns a string"
  value       = fortios_dnsfilter_profile.this.sdns_ftgd_err_log
}

output "youtube_restrict" {
  description = "returns a string"
  value       = fortios_dnsfilter_profile.this.youtube_restrict
}

output "this" {
  value = fortios_dnsfilter_profile.this
}
```

[top](#index)