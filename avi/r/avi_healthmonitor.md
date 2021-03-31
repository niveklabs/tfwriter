# avi_healthmonitor

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
module "avi_healthmonitor" {
  source = "./modules/avi/r/avi_healthmonitor"

  # allow_duplicate_monitors - (optional) is a type of bool
  allow_duplicate_monitors = null
  # description - (optional) is a type of string
  description = null
  # disable_quickstart - (optional) is a type of bool
  disable_quickstart = null
  # failed_checks - (optional) is a type of number
  failed_checks = null
  # is_federated - (optional) is a type of bool
  is_federated = null
  # monitor_port - (optional) is a type of number
  monitor_port = null
  # name - (required) is a type of string
  name = null
  # receive_timeout - (optional) is a type of number
  receive_timeout = null
  # send_interval - (optional) is a type of number
  send_interval = null
  # successful_checks - (optional) is a type of number
  successful_checks = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # type - (required) is a type of string
  type = null
  # uuid - (optional) is a type of string
  uuid = null

  dns_monitor = [{
    qtype           = null
    query_name      = null
    rcode           = null
    record_type     = null
    response_string = null
  }]

  external_monitor = [{
    command_code       = null
    command_parameters = null
    command_path       = null
    command_variables  = null
  }]

  http_monitor = [{
    exact_http_request   = null
    http_request         = null
    http_response        = null
    http_response_code   = []
    maintenance_code     = []
    maintenance_response = null
    ssl_attributes = [{
      pki_profile_ref             = null
      server_name                 = null
      ssl_key_and_certificate_ref = null
      ssl_profile_ref             = null
    }]
  }]

  https_monitor = [{
    exact_http_request   = null
    http_request         = null
    http_response        = null
    http_response_code   = []
    maintenance_code     = []
    maintenance_response = null
    ssl_attributes = [{
      pki_profile_ref             = null
      server_name                 = null
      ssl_key_and_certificate_ref = null
      ssl_profile_ref             = null
    }]
  }]

  radius_monitor = [{
    password      = null
    shared_secret = null
    username      = null
  }]

  sip_monitor = [{
    sip_monitor_transport = null
    sip_request_code      = null
    sip_response          = null
  }]

  tcp_monitor = [{
    maintenance_response = null
    tcp_half_open        = null
    tcp_request          = null
    tcp_response         = null
  }]

  udp_monitor = [{
    maintenance_response = null
    udp_request          = null
    udp_response         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_duplicate_monitors" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_quickstart" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "failed_checks" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "is_federated" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "monitor_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "receive_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "send_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "successful_checks" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_monitor" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      qtype           = string
      query_name      = string
      rcode           = string
      record_type     = string
      response_string = string
    }
  ))
  default = []
}

variable "external_monitor" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      command_code       = string
      command_parameters = string
      command_path       = string
      command_variables  = string
    }
  ))
  default = []
}

variable "http_monitor" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      exact_http_request   = bool
      http_request         = string
      http_response        = string
      http_response_code   = list(string)
      maintenance_code     = list(number)
      maintenance_response = string
      ssl_attributes = set(object(
        {
          pki_profile_ref             = string
          server_name                 = string
          ssl_key_and_certificate_ref = string
          ssl_profile_ref             = string
        }
      ))
    }
  ))
  default = []
}

variable "https_monitor" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      exact_http_request   = bool
      http_request         = string
      http_response        = string
      http_response_code   = list(string)
      maintenance_code     = list(number)
      maintenance_response = string
      ssl_attributes = set(object(
        {
          pki_profile_ref             = string
          server_name                 = string
          ssl_key_and_certificate_ref = string
          ssl_profile_ref             = string
        }
      ))
    }
  ))
  default = []
}

variable "radius_monitor" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      password      = string
      shared_secret = string
      username      = string
    }
  ))
  default = []
}

variable "sip_monitor" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      sip_monitor_transport = string
      sip_request_code      = string
      sip_response          = string
    }
  ))
  default = []
}

variable "tcp_monitor" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      maintenance_response = string
      tcp_half_open        = bool
      tcp_request          = string
      tcp_response         = string
    }
  ))
  default = []
}

variable "udp_monitor" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      maintenance_response = string
      udp_request          = string
      udp_response         = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_healthmonitor" "this" {
  allow_duplicate_monitors = var.allow_duplicate_monitors
  description              = var.description
  disable_quickstart       = var.disable_quickstart
  failed_checks            = var.failed_checks
  is_federated             = var.is_federated
  monitor_port             = var.monitor_port
  name                     = var.name
  receive_timeout          = var.receive_timeout
  send_interval            = var.send_interval
  successful_checks        = var.successful_checks
  tenant_ref               = var.tenant_ref
  type                     = var.type
  uuid                     = var.uuid

  dynamic "dns_monitor" {
    for_each = var.dns_monitor
    content {
      qtype           = dns_monitor.value["qtype"]
      query_name      = dns_monitor.value["query_name"]
      rcode           = dns_monitor.value["rcode"]
      record_type     = dns_monitor.value["record_type"]
      response_string = dns_monitor.value["response_string"]
    }
  }

  dynamic "external_monitor" {
    for_each = var.external_monitor
    content {
      command_code       = external_monitor.value["command_code"]
      command_parameters = external_monitor.value["command_parameters"]
      command_path       = external_monitor.value["command_path"]
      command_variables  = external_monitor.value["command_variables"]
    }
  }

  dynamic "http_monitor" {
    for_each = var.http_monitor
    content {
      exact_http_request   = http_monitor.value["exact_http_request"]
      http_request         = http_monitor.value["http_request"]
      http_response        = http_monitor.value["http_response"]
      http_response_code   = http_monitor.value["http_response_code"]
      maintenance_code     = http_monitor.value["maintenance_code"]
      maintenance_response = http_monitor.value["maintenance_response"]

      dynamic "ssl_attributes" {
        for_each = http_monitor.value.ssl_attributes
        content {
          pki_profile_ref             = ssl_attributes.value["pki_profile_ref"]
          server_name                 = ssl_attributes.value["server_name"]
          ssl_key_and_certificate_ref = ssl_attributes.value["ssl_key_and_certificate_ref"]
          ssl_profile_ref             = ssl_attributes.value["ssl_profile_ref"]
        }
      }

    }
  }

  dynamic "https_monitor" {
    for_each = var.https_monitor
    content {
      exact_http_request   = https_monitor.value["exact_http_request"]
      http_request         = https_monitor.value["http_request"]
      http_response        = https_monitor.value["http_response"]
      http_response_code   = https_monitor.value["http_response_code"]
      maintenance_code     = https_monitor.value["maintenance_code"]
      maintenance_response = https_monitor.value["maintenance_response"]

      dynamic "ssl_attributes" {
        for_each = https_monitor.value.ssl_attributes
        content {
          pki_profile_ref             = ssl_attributes.value["pki_profile_ref"]
          server_name                 = ssl_attributes.value["server_name"]
          ssl_key_and_certificate_ref = ssl_attributes.value["ssl_key_and_certificate_ref"]
          ssl_profile_ref             = ssl_attributes.value["ssl_profile_ref"]
        }
      }

    }
  }

  dynamic "radius_monitor" {
    for_each = var.radius_monitor
    content {
      password      = radius_monitor.value["password"]
      shared_secret = radius_monitor.value["shared_secret"]
      username      = radius_monitor.value["username"]
    }
  }

  dynamic "sip_monitor" {
    for_each = var.sip_monitor
    content {
      sip_monitor_transport = sip_monitor.value["sip_monitor_transport"]
      sip_request_code      = sip_monitor.value["sip_request_code"]
      sip_response          = sip_monitor.value["sip_response"]
    }
  }

  dynamic "tcp_monitor" {
    for_each = var.tcp_monitor
    content {
      maintenance_response = tcp_monitor.value["maintenance_response"]
      tcp_half_open        = tcp_monitor.value["tcp_half_open"]
      tcp_request          = tcp_monitor.value["tcp_request"]
      tcp_response         = tcp_monitor.value["tcp_response"]
    }
  }

  dynamic "udp_monitor" {
    for_each = var.udp_monitor
    content {
      maintenance_response = udp_monitor.value["maintenance_response"]
      udp_request          = udp_monitor.value["udp_request"]
      udp_response         = udp_monitor.value["udp_response"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_duplicate_monitors" {
  description = "returns a bool"
  value       = avi_healthmonitor.this.allow_duplicate_monitors
}

output "description" {
  description = "returns a string"
  value       = avi_healthmonitor.this.description
}

output "disable_quickstart" {
  description = "returns a bool"
  value       = avi_healthmonitor.this.disable_quickstart
}

output "id" {
  description = "returns a string"
  value       = avi_healthmonitor.this.id
}

output "monitor_port" {
  description = "returns a number"
  value       = avi_healthmonitor.this.monitor_port
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_healthmonitor.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_healthmonitor.this.uuid
}

output "this" {
  value = avi_healthmonitor.this
}
```

[top](#index)