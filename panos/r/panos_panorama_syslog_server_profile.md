# panos_panorama_syslog_server_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_syslog_server_profile" {
  source = "./modules/panos/r/panos_panorama_syslog_server_profile"

  # auth_format - (optional) is a type of string
  auth_format = null
  # config_format - (optional) is a type of string
  config_format = null
  # data_format - (optional) is a type of string
  data_format = null
  # device_group - (optional) is a type of string
  device_group = null
  # escape_character - (optional) is a type of string
  escape_character = null
  # escaped_characters - (optional) is a type of string
  escaped_characters = null
  # gtp_format - (optional) is a type of string
  gtp_format = null
  # hip_match_format - (optional) is a type of string
  hip_match_format = null
  # iptag_format - (optional) is a type of string
  iptag_format = null
  # name - (required) is a type of string
  name = null
  # sctp_format - (optional) is a type of string
  sctp_format = null
  # system_format - (optional) is a type of string
  system_format = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # threat_format - (optional) is a type of string
  threat_format = null
  # traffic_format - (optional) is a type of string
  traffic_format = null
  # tunnel_format - (optional) is a type of string
  tunnel_format = null
  # url_format - (optional) is a type of string
  url_format = null
  # user_id_format - (optional) is a type of string
  user_id_format = null
  # vsys - (optional) is a type of string
  vsys = null
  # wildfire_format - (optional) is a type of string
  wildfire_format = null

  syslog_server = [{
    facility      = null
    name          = null
    port          = null
    server        = null
    syslog_format = null
    transport     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auth_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "config_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "escape_character" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "escaped_characters" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gtp_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hip_match_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iptag_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "sctp_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_stack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "threat_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tunnel_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_id_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wildfire_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "syslog_server" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      facility      = string
      name          = string
      port          = number
      server        = string
      syslog_format = string
      transport     = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_syslog_server_profile" "this" {
  auth_format        = var.auth_format
  config_format      = var.config_format
  data_format        = var.data_format
  device_group       = var.device_group
  escape_character   = var.escape_character
  escaped_characters = var.escaped_characters
  gtp_format         = var.gtp_format
  hip_match_format   = var.hip_match_format
  iptag_format       = var.iptag_format
  name               = var.name
  sctp_format        = var.sctp_format
  system_format      = var.system_format
  template           = var.template
  template_stack     = var.template_stack
  threat_format      = var.threat_format
  traffic_format     = var.traffic_format
  tunnel_format      = var.tunnel_format
  url_format         = var.url_format
  user_id_format     = var.user_id_format
  vsys               = var.vsys
  wildfire_format    = var.wildfire_format

  dynamic "syslog_server" {
    for_each = var.syslog_server
    content {
      facility      = syslog_server.value["facility"]
      name          = syslog_server.value["name"]
      port          = syslog_server.value["port"]
      server        = syslog_server.value["server"]
      syslog_format = syslog_server.value["syslog_format"]
      transport     = syslog_server.value["transport"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_syslog_server_profile.this.id
}

output "this" {
  value = panos_panorama_syslog_server_profile.this
}
```

[top](#index)