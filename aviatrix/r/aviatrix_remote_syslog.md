# aviatrix_remote_syslog

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_remote_syslog" {
  source = "./modules/aviatrix/r/aviatrix_remote_syslog"

  # ca_certificate_file - (optional) is a type of string
  ca_certificate_file = null
  # excluded_gateways - (optional) is a type of set of string
  excluded_gateways = []
  # index - (optional) is a type of number
  index = null
  # port - (required) is a type of number
  port = null
  # private_key_file - (optional) is a type of string
  private_key_file = null
  # protocol - (optional) is a type of string
  protocol = null
  # public_certificate_file - (optional) is a type of string
  public_certificate_file = null
  # server - (required) is a type of string
  server = null
  # template - (optional) is a type of string
  template = null
}
```

[top](#index)

### Variables

```terraform
variable "ca_certificate_file" {
  description = "(optional) - CA certificate file."
  type        = string
  default     = null
}

variable "excluded_gateways" {
  description = "(optional) - List of excluded gateways."
  type        = set(string)
  default     = null
}

variable "index" {
  description = "(optional) - A total of 10 profiles from index 0 to 9 are supported for remote syslog, while index 9 is reserved for CoPilot."
  type        = number
  default     = null
}

variable "port" {
  description = "(required) - Listening port of the remote syslog server."
  type        = number
}

variable "private_key_file" {
  description = "(optional) - Private key of the controller that pairs with the public certificate."
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional) - TCP or UDP (TCP by default)."
  type        = string
  default     = null
}

variable "public_certificate_file" {
  description = "(optional) - Public certificate of the controller signed by the same CA."
  type        = string
  default     = null
}

variable "server" {
  description = "(required) - FQDN or IP address of the remote syslog server."
  type        = string
}

variable "template" {
  description = "(optional) - Useful when forwarding to 3rd party servers like Datadog or Sumo"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_remote_syslog" "this" {
  # ca_certificate_file - (optional) is a type of string
  ca_certificate_file = var.ca_certificate_file
  # excluded_gateways - (optional) is a type of set of string
  excluded_gateways = var.excluded_gateways
  # index - (optional) is a type of number
  index = var.index
  # port - (required) is a type of number
  port = var.port
  # private_key_file - (optional) is a type of string
  private_key_file = var.private_key_file
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # public_certificate_file - (optional) is a type of string
  public_certificate_file = var.public_certificate_file
  # server - (required) is a type of string
  server = var.server
  # template - (optional) is a type of string
  template = var.template
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_remote_syslog.this.id
}

output "notls" {
  description = "returns a bool"
  value       = aviatrix_remote_syslog.this.notls
}

output "status" {
  description = "returns a string"
  value       = aviatrix_remote_syslog.this.status
}

output "this" {
  value = aviatrix_remote_syslog.this
}
```

[top](#index)