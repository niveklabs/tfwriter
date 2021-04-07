# panos_panorama_http_server_profile

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
module "panos_panorama_http_server_profile" {
  source = "./modules/panos/r/panos_panorama_http_server_profile"

  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # tag_registration - (optional) is a type of bool
  tag_registration = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # vsys - (optional) is a type of string
  vsys = null

  auth_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]

  config_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]

  data_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]

  gtp_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]

  hip_match_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]

  http_server = [{
    address             = null
    certificate_profile = null
    http_method         = null
    name                = null
    password            = null
    port                = null
    protocol            = null
    tls_version         = null
    username            = null
  }]

  iptag_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]

  sctp_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]

  system_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]

  threat_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]

  traffic_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]

  tunnel_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]

  url_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]

  user_id_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]

  wildfire_format = [{
    headers    = {}
    name       = null
    params     = {}
    payload    = null
    uri_format = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tag_registration" {
  description = "(optional)"
  type        = bool
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

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}

variable "config_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}

variable "data_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}

variable "gtp_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}

variable "hip_match_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}

variable "http_server" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      address             = string
      certificate_profile = string
      http_method         = string
      name                = string
      password            = string
      port                = number
      protocol            = string
      tls_version         = string
      username            = string
    }
  ))
}

variable "iptag_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}

variable "sctp_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}

variable "system_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}

variable "threat_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}

variable "traffic_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}

variable "tunnel_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}

variable "url_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}

variable "user_id_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}

variable "wildfire_format" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      headers    = map(string)
      name       = string
      params     = map(string)
      payload    = string
      uri_format = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_http_server_profile" "this" {
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # name - (required) is a type of string
  name = var.name
  # tag_registration - (optional) is a type of bool
  tag_registration = var.tag_registration
  # template - (optional) is a type of string
  template = var.template
  # template_stack - (optional) is a type of string
  template_stack = var.template_stack
  # vsys - (optional) is a type of string
  vsys = var.vsys

  dynamic "auth_format" {
    for_each = var.auth_format
    content {
      # headers - (optional) is a type of map of string
      headers = auth_format.value["headers"]
      # name - (optional) is a type of string
      name = auth_format.value["name"]
      # params - (optional) is a type of map of string
      params = auth_format.value["params"]
      # payload - (optional) is a type of string
      payload = auth_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = auth_format.value["uri_format"]
    }
  }

  dynamic "config_format" {
    for_each = var.config_format
    content {
      # headers - (optional) is a type of map of string
      headers = config_format.value["headers"]
      # name - (optional) is a type of string
      name = config_format.value["name"]
      # params - (optional) is a type of map of string
      params = config_format.value["params"]
      # payload - (optional) is a type of string
      payload = config_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = config_format.value["uri_format"]
    }
  }

  dynamic "data_format" {
    for_each = var.data_format
    content {
      # headers - (optional) is a type of map of string
      headers = data_format.value["headers"]
      # name - (optional) is a type of string
      name = data_format.value["name"]
      # params - (optional) is a type of map of string
      params = data_format.value["params"]
      # payload - (optional) is a type of string
      payload = data_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = data_format.value["uri_format"]
    }
  }

  dynamic "gtp_format" {
    for_each = var.gtp_format
    content {
      # headers - (optional) is a type of map of string
      headers = gtp_format.value["headers"]
      # name - (optional) is a type of string
      name = gtp_format.value["name"]
      # params - (optional) is a type of map of string
      params = gtp_format.value["params"]
      # payload - (optional) is a type of string
      payload = gtp_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = gtp_format.value["uri_format"]
    }
  }

  dynamic "hip_match_format" {
    for_each = var.hip_match_format
    content {
      # headers - (optional) is a type of map of string
      headers = hip_match_format.value["headers"]
      # name - (optional) is a type of string
      name = hip_match_format.value["name"]
      # params - (optional) is a type of map of string
      params = hip_match_format.value["params"]
      # payload - (optional) is a type of string
      payload = hip_match_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = hip_match_format.value["uri_format"]
    }
  }

  dynamic "http_server" {
    for_each = var.http_server
    content {
      # address - (required) is a type of string
      address = http_server.value["address"]
      # certificate_profile - (optional) is a type of string
      certificate_profile = http_server.value["certificate_profile"]
      # http_method - (optional) is a type of string
      http_method = http_server.value["http_method"]
      # name - (required) is a type of string
      name = http_server.value["name"]
      # password - (optional) is a type of string
      password = http_server.value["password"]
      # port - (optional) is a type of number
      port = http_server.value["port"]
      # protocol - (optional) is a type of string
      protocol = http_server.value["protocol"]
      # tls_version - (optional) is a type of string
      tls_version = http_server.value["tls_version"]
      # username - (optional) is a type of string
      username = http_server.value["username"]
    }
  }

  dynamic "iptag_format" {
    for_each = var.iptag_format
    content {
      # headers - (optional) is a type of map of string
      headers = iptag_format.value["headers"]
      # name - (optional) is a type of string
      name = iptag_format.value["name"]
      # params - (optional) is a type of map of string
      params = iptag_format.value["params"]
      # payload - (optional) is a type of string
      payload = iptag_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = iptag_format.value["uri_format"]
    }
  }

  dynamic "sctp_format" {
    for_each = var.sctp_format
    content {
      # headers - (optional) is a type of map of string
      headers = sctp_format.value["headers"]
      # name - (optional) is a type of string
      name = sctp_format.value["name"]
      # params - (optional) is a type of map of string
      params = sctp_format.value["params"]
      # payload - (optional) is a type of string
      payload = sctp_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = sctp_format.value["uri_format"]
    }
  }

  dynamic "system_format" {
    for_each = var.system_format
    content {
      # headers - (optional) is a type of map of string
      headers = system_format.value["headers"]
      # name - (optional) is a type of string
      name = system_format.value["name"]
      # params - (optional) is a type of map of string
      params = system_format.value["params"]
      # payload - (optional) is a type of string
      payload = system_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = system_format.value["uri_format"]
    }
  }

  dynamic "threat_format" {
    for_each = var.threat_format
    content {
      # headers - (optional) is a type of map of string
      headers = threat_format.value["headers"]
      # name - (optional) is a type of string
      name = threat_format.value["name"]
      # params - (optional) is a type of map of string
      params = threat_format.value["params"]
      # payload - (optional) is a type of string
      payload = threat_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = threat_format.value["uri_format"]
    }
  }

  dynamic "traffic_format" {
    for_each = var.traffic_format
    content {
      # headers - (optional) is a type of map of string
      headers = traffic_format.value["headers"]
      # name - (optional) is a type of string
      name = traffic_format.value["name"]
      # params - (optional) is a type of map of string
      params = traffic_format.value["params"]
      # payload - (optional) is a type of string
      payload = traffic_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = traffic_format.value["uri_format"]
    }
  }

  dynamic "tunnel_format" {
    for_each = var.tunnel_format
    content {
      # headers - (optional) is a type of map of string
      headers = tunnel_format.value["headers"]
      # name - (optional) is a type of string
      name = tunnel_format.value["name"]
      # params - (optional) is a type of map of string
      params = tunnel_format.value["params"]
      # payload - (optional) is a type of string
      payload = tunnel_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = tunnel_format.value["uri_format"]
    }
  }

  dynamic "url_format" {
    for_each = var.url_format
    content {
      # headers - (optional) is a type of map of string
      headers = url_format.value["headers"]
      # name - (optional) is a type of string
      name = url_format.value["name"]
      # params - (optional) is a type of map of string
      params = url_format.value["params"]
      # payload - (optional) is a type of string
      payload = url_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = url_format.value["uri_format"]
    }
  }

  dynamic "user_id_format" {
    for_each = var.user_id_format
    content {
      # headers - (optional) is a type of map of string
      headers = user_id_format.value["headers"]
      # name - (optional) is a type of string
      name = user_id_format.value["name"]
      # params - (optional) is a type of map of string
      params = user_id_format.value["params"]
      # payload - (optional) is a type of string
      payload = user_id_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = user_id_format.value["uri_format"]
    }
  }

  dynamic "wildfire_format" {
    for_each = var.wildfire_format
    content {
      # headers - (optional) is a type of map of string
      headers = wildfire_format.value["headers"]
      # name - (optional) is a type of string
      name = wildfire_format.value["name"]
      # params - (optional) is a type of map of string
      params = wildfire_format.value["params"]
      # payload - (optional) is a type of string
      payload = wildfire_format.value["payload"]
      # uri_format - (optional) is a type of string
      uri_format = wildfire_format.value["uri_format"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_http_server_profile.this.id
}

output "password_enc" {
  description = "returns a map of string"
  value       = panos_panorama_http_server_profile.this.password_enc
  sensitive   = true
}

output "password_raw" {
  description = "returns a map of string"
  value       = panos_panorama_http_server_profile.this.password_raw
  sensitive   = true
}

output "this" {
  value = panos_panorama_http_server_profile.this
}
```

[top](#index)