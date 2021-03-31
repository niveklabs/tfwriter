# avi_alertsyslogconfig

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_alertsyslogconfig" {
  source = "./modules/avi/r/avi_alertsyslogconfig"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  syslog_servers = [{
    anon_auth                   = null
    format                      = null
    pkiprofile_ref              = null
    ssl_key_and_certificate_ref = null
    syslog_server               = null
    syslog_server_port          = null
    tls_enable                  = null
    udp                         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "syslog_servers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      anon_auth                   = bool
      format                      = string
      pkiprofile_ref              = string
      ssl_key_and_certificate_ref = string
      syslog_server               = string
      syslog_server_port          = number
      tls_enable                  = bool
      udp                         = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_alertsyslogconfig" "this" {
  description = var.description
  name        = var.name
  tenant_ref  = var.tenant_ref
  uuid        = var.uuid

  dynamic "syslog_servers" {
    for_each = var.syslog_servers
    content {
      anon_auth                   = syslog_servers.value["anon_auth"]
      format                      = syslog_servers.value["format"]
      pkiprofile_ref              = syslog_servers.value["pkiprofile_ref"]
      ssl_key_and_certificate_ref = syslog_servers.value["ssl_key_and_certificate_ref"]
      syslog_server               = syslog_servers.value["syslog_server"]
      syslog_server_port          = syslog_servers.value["syslog_server_port"]
      tls_enable                  = syslog_servers.value["tls_enable"]
      udp                         = syslog_servers.value["udp"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_alertsyslogconfig.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_alertsyslogconfig.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_alertsyslogconfig.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_alertsyslogconfig.this.uuid
}

output "this" {
  value = avi_alertsyslogconfig.this
}
```

[top](#index)