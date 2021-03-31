# fortios_wanopt_profile

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
module "fortios_wanopt_profile" {
  source = "./modules/fortios/r/fortios_wanopt_profile"

  # auth_group - (optional) is a type of string
  auth_group = null
  # comments - (optional) is a type of string
  comments = null
  # name - (optional) is a type of string
  name = null
  # transparent - (optional) is a type of string
  transparent = null

  cifs = [{
    byte_caching    = null
    log_traffic     = null
    port            = null
    prefer_chunking = null
    protocol_opt    = null
    secure_tunnel   = null
    status          = null
    tunnel_sharing  = null
  }]

  ftp = [{
    byte_caching    = null
    log_traffic     = null
    port            = null
    prefer_chunking = null
    protocol_opt    = null
    secure_tunnel   = null
    ssl             = null
    status          = null
    tunnel_sharing  = null
  }]

  http = [{
    byte_caching         = null
    log_traffic          = null
    port                 = null
    prefer_chunking      = null
    protocol_opt         = null
    secure_tunnel        = null
    ssl                  = null
    ssl_port             = null
    status               = null
    tunnel_non_http      = null
    tunnel_sharing       = null
    unknown_http_version = null
  }]

  mapi = [{
    byte_caching   = null
    log_traffic    = null
    port           = null
    secure_tunnel  = null
    status         = null
    tunnel_sharing = null
  }]

  tcp = [{
    byte_caching     = null
    byte_caching_opt = null
    log_traffic      = null
    port             = null
    secure_tunnel    = null
    ssl              = null
    ssl_port         = null
    status           = null
    tunnel_sharing   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auth_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "transparent" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cifs" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      byte_caching    = string
      log_traffic     = string
      port            = number
      prefer_chunking = string
      protocol_opt    = string
      secure_tunnel   = string
      status          = string
      tunnel_sharing  = string
    }
  ))
  default = []
}

variable "ftp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      byte_caching    = string
      log_traffic     = string
      port            = number
      prefer_chunking = string
      protocol_opt    = string
      secure_tunnel   = string
      ssl             = string
      status          = string
      tunnel_sharing  = string
    }
  ))
  default = []
}

variable "http" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      byte_caching         = string
      log_traffic          = string
      port                 = number
      prefer_chunking      = string
      protocol_opt         = string
      secure_tunnel        = string
      ssl                  = string
      ssl_port             = number
      status               = string
      tunnel_non_http      = string
      tunnel_sharing       = string
      unknown_http_version = string
    }
  ))
  default = []
}

variable "mapi" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      byte_caching   = string
      log_traffic    = string
      port           = number
      secure_tunnel  = string
      status         = string
      tunnel_sharing = string
    }
  ))
  default = []
}

variable "tcp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      byte_caching     = string
      byte_caching_opt = string
      log_traffic      = string
      port             = string
      secure_tunnel    = string
      ssl              = string
      ssl_port         = number
      status           = string
      tunnel_sharing   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wanopt_profile" "this" {
  auth_group  = var.auth_group
  comments    = var.comments
  name        = var.name
  transparent = var.transparent

  dynamic "cifs" {
    for_each = var.cifs
    content {
      byte_caching    = cifs.value["byte_caching"]
      log_traffic     = cifs.value["log_traffic"]
      port            = cifs.value["port"]
      prefer_chunking = cifs.value["prefer_chunking"]
      protocol_opt    = cifs.value["protocol_opt"]
      secure_tunnel   = cifs.value["secure_tunnel"]
      status          = cifs.value["status"]
      tunnel_sharing  = cifs.value["tunnel_sharing"]
    }
  }

  dynamic "ftp" {
    for_each = var.ftp
    content {
      byte_caching    = ftp.value["byte_caching"]
      log_traffic     = ftp.value["log_traffic"]
      port            = ftp.value["port"]
      prefer_chunking = ftp.value["prefer_chunking"]
      protocol_opt    = ftp.value["protocol_opt"]
      secure_tunnel   = ftp.value["secure_tunnel"]
      ssl             = ftp.value["ssl"]
      status          = ftp.value["status"]
      tunnel_sharing  = ftp.value["tunnel_sharing"]
    }
  }

  dynamic "http" {
    for_each = var.http
    content {
      byte_caching         = http.value["byte_caching"]
      log_traffic          = http.value["log_traffic"]
      port                 = http.value["port"]
      prefer_chunking      = http.value["prefer_chunking"]
      protocol_opt         = http.value["protocol_opt"]
      secure_tunnel        = http.value["secure_tunnel"]
      ssl                  = http.value["ssl"]
      ssl_port             = http.value["ssl_port"]
      status               = http.value["status"]
      tunnel_non_http      = http.value["tunnel_non_http"]
      tunnel_sharing       = http.value["tunnel_sharing"]
      unknown_http_version = http.value["unknown_http_version"]
    }
  }

  dynamic "mapi" {
    for_each = var.mapi
    content {
      byte_caching   = mapi.value["byte_caching"]
      log_traffic    = mapi.value["log_traffic"]
      port           = mapi.value["port"]
      secure_tunnel  = mapi.value["secure_tunnel"]
      status         = mapi.value["status"]
      tunnel_sharing = mapi.value["tunnel_sharing"]
    }
  }

  dynamic "tcp" {
    for_each = var.tcp
    content {
      byte_caching     = tcp.value["byte_caching"]
      byte_caching_opt = tcp.value["byte_caching_opt"]
      log_traffic      = tcp.value["log_traffic"]
      port             = tcp.value["port"]
      secure_tunnel    = tcp.value["secure_tunnel"]
      ssl              = tcp.value["ssl"]
      ssl_port         = tcp.value["ssl_port"]
      status           = tcp.value["status"]
      tunnel_sharing   = tcp.value["tunnel_sharing"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auth_group" {
  description = "returns a string"
  value       = fortios_wanopt_profile.this.auth_group
}

output "id" {
  description = "returns a string"
  value       = fortios_wanopt_profile.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wanopt_profile.this.name
}

output "transparent" {
  description = "returns a string"
  value       = fortios_wanopt_profile.this.transparent
}

output "this" {
  value = fortios_wanopt_profile.this
}
```

[top](#index)