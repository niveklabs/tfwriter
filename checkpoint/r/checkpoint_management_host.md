# checkpoint_management_host

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_host" {
  source = "./modules/checkpoint/r/checkpoint_management_host"

  # color - (optional) is a type of string
  color = null
  # comments - (optional) is a type of string
  comments = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # ipv4_address - (optional) is a type of string
  ipv4_address = null
  # ipv6_address - (optional) is a type of string
  ipv6_address = null
  # name - (required) is a type of string
  name = null
  # nat_settings - (optional) is a type of map of string
  nat_settings = {}
  # tags - (optional) is a type of set of string
  tags = []

  host_servers = [{
    dns_server  = null
    mail_server = null
    web_server  = null
    web_server_config = [{
      additional_ports     = []
      application_engines  = []
      listen_standard_port = null
      operating_system     = null
      protected_by         = null
    }]
  }]

  interfaces = [{
    color           = null
    comments        = null
    ignore_errors   = null
    ignore_warnings = null
    mask_length4    = null
    mask_length6    = null
    name            = null
    subnet4         = null
    subnet6         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "color" {
  description = "(optional) - Color of the object. Should be one of existing colors."
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "ignore_errors" {
  description = "(optional) - Apply changes ignoring errors. You won't be able to publish such a changes. If ignore-warnings flag was omitted - warnings will also be ignored."
  type        = bool
  default     = null
}

variable "ignore_warnings" {
  description = "(optional) - Apply changes ignoring warnings."
  type        = bool
  default     = null
}

variable "ipv4_address" {
  description = "(optional) - IPv4 address."
  type        = string
  default     = null
}

variable "ipv6_address" {
  description = "(optional) - IPv6 address."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Object name. Should be unique in the domain."
  type        = string
}

variable "nat_settings" {
  description = "(optional) - NAT settings."
  type        = map(string)
  default     = null
}

variable "tags" {
  description = "(optional) - Collection of tag identifiers."
  type        = set(string)
  default     = null
}

variable "host_servers" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dns_server  = bool
      mail_server = bool
      web_server  = bool
      web_server_config = list(object(
        {
          additional_ports     = set(string)
          application_engines  = set(string)
          listen_standard_port = bool
          operating_system     = string
          protected_by         = string
        }
      ))
    }
  ))
  default = []
}

variable "interfaces" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      color           = string
      comments        = string
      ignore_errors   = bool
      ignore_warnings = bool
      mask_length4    = number
      mask_length6    = number
      name            = string
      subnet4         = string
      subnet6         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_host" "this" {
  color           = var.color
  comments        = var.comments
  ignore_errors   = var.ignore_errors
  ignore_warnings = var.ignore_warnings
  ipv4_address    = var.ipv4_address
  ipv6_address    = var.ipv6_address
  name            = var.name
  nat_settings    = var.nat_settings
  tags            = var.tags

  dynamic "host_servers" {
    for_each = var.host_servers
    content {
      dns_server  = host_servers.value["dns_server"]
      mail_server = host_servers.value["mail_server"]
      web_server  = host_servers.value["web_server"]

      dynamic "web_server_config" {
        for_each = host_servers.value.web_server_config
        content {
          additional_ports     = web_server_config.value["additional_ports"]
          application_engines  = web_server_config.value["application_engines"]
          listen_standard_port = web_server_config.value["listen_standard_port"]
          operating_system     = web_server_config.value["operating_system"]
          protected_by         = web_server_config.value["protected_by"]
        }
      }

    }
  }

  dynamic "interfaces" {
    for_each = var.interfaces
    content {
      color           = interfaces.value["color"]
      comments        = interfaces.value["comments"]
      ignore_errors   = interfaces.value["ignore_errors"]
      ignore_warnings = interfaces.value["ignore_warnings"]
      mask_length4    = interfaces.value["mask_length4"]
      mask_length6    = interfaces.value["mask_length6"]
      name            = interfaces.value["name"]
      subnet4         = interfaces.value["subnet4"]
      subnet6         = interfaces.value["subnet6"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_host.this.id
}

output "this" {
  value = checkpoint_management_host.this
}
```

[top](#index)