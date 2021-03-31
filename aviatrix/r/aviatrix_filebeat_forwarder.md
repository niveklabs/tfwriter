# aviatrix_filebeat_forwarder

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
module "aviatrix_filebeat_forwarder" {
  source = "./modules/aviatrix/r/aviatrix_filebeat_forwarder"

  # config_file - (optional) is a type of string
  config_file = null
  # excluded_gateways - (optional) is a type of set of string
  excluded_gateways = []
  # port - (required) is a type of number
  port = null
  # server - (required) is a type of string
  server = null
  # trusted_ca_file - (optional) is a type of string
  trusted_ca_file = null
}
```

[top](#index)

### Variables

```terraform
variable "config_file" {
  description = "(optional) - Configuration file."
  type        = string
  default     = null
}

variable "excluded_gateways" {
  description = "(optional) - List of excluded gateways."
  type        = set(string)
  default     = null
}

variable "port" {
  description = "(required) - Port number."
  type        = number
}

variable "server" {
  description = "(required) - Server IP."
  type        = string
}

variable "trusted_ca_file" {
  description = "(optional) - Trusted CA file."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_filebeat_forwarder" "this" {
  config_file       = var.config_file
  excluded_gateways = var.excluded_gateways
  port              = var.port
  server            = var.server
  trusted_ca_file   = var.trusted_ca_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_filebeat_forwarder.this.id
}

output "status" {
  description = "returns a string"
  value       = aviatrix_filebeat_forwarder.this.status
}

output "this" {
  value = aviatrix_filebeat_forwarder.this
}
```

[top](#index)