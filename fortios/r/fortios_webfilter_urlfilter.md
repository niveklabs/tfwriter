# fortios_webfilter_urlfilter

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
module "fortios_webfilter_urlfilter" {
  source = "./modules/fortios/r/fortios_webfilter_urlfilter"

  # comment - (optional) is a type of string
  comment = null
  # fosid - (required) is a type of number
  fosid = null
  # ip_addr_block - (optional) is a type of string
  ip_addr_block = null
  # name - (required) is a type of string
  name = null
  # one_arm_ips_urlfilter - (optional) is a type of string
  one_arm_ips_urlfilter = null

  entries = [{
    action             = null
    dns_address_family = null
    exempt             = null
    id                 = null
    referrer_host      = null
    status             = null
    type               = null
    url                = null
    web_proxy_profile  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(required)"
  type        = number
}

variable "ip_addr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "one_arm_ips_urlfilter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "entries" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action             = string
      dns_address_family = string
      exempt             = string
      id                 = number
      referrer_host      = string
      status             = string
      type               = string
      url                = string
      web_proxy_profile  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webfilter_urlfilter" "this" {
  comment               = var.comment
  fosid                 = var.fosid
  ip_addr_block         = var.ip_addr_block
  name                  = var.name
  one_arm_ips_urlfilter = var.one_arm_ips_urlfilter

  dynamic "entries" {
    for_each = var.entries
    content {
      action             = entries.value["action"]
      dns_address_family = entries.value["dns_address_family"]
      exempt             = entries.value["exempt"]
      id                 = entries.value["id"]
      referrer_host      = entries.value["referrer_host"]
      status             = entries.value["status"]
      type               = entries.value["type"]
      url                = entries.value["url"]
      web_proxy_profile  = entries.value["web_proxy_profile"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_webfilter_urlfilter.this.id
}

output "ip_addr_block" {
  description = "returns a string"
  value       = fortios_webfilter_urlfilter.this.ip_addr_block
}

output "one_arm_ips_urlfilter" {
  description = "returns a string"
  value       = fortios_webfilter_urlfilter.this.one_arm_ips_urlfilter
}

output "this" {
  value = fortios_webfilter_urlfilter.this
}
```

[top](#index)